# gsi-flash-guide-all
# Flash any GSI on Any Realme Phone Without Root | সহজে Android GSI ROM ফ্ল্যাশ টিউটোরিয়াল 

[**Latest Release**](https://github.com/kafi05/KAFI-777-GUIDE-2.0/releases/latest)

**Author:** [@kafi05](https://github.com/kafi05)

<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/34a6d871-b491-420b-8c2b-4a745c8abc68" />

---

## 📂 Downloads

* [Treble Info](https://f-droid.org/packages/tk.hack5.treblecheck/)

## 🔗 Recommended Android 16 GSI Links

* [Official Google Android 16 GSI](https://developer.android.com/topic/generic-system-image/releases#android-gsi-16)
* [EvolutionX](https://github.com/Doze-off/EvoX_treble/releases/tag/2025-07-06)
* [CrDroid](https://github.com/Doze-off/crdroid_gsi_treble/releases)
* [DerpFest](https://github.com/Doze-off/Derpfest_treble/releases/tag/2025-07-07)
* [PixelOS](https://github.com/mytja/treble_pixelos/releases/tag/20250806)
* [YAAP](https://github.com/Doze-off/YAAP_treble/releases/tag/2025-06-29)
* [VoltageOS](https://github.com/Doze-off/voltage_a16_treble/releases/tag/2025-07-08)
* [InfinityX](https://github.com/Doze-off/ProjectInfinity-X_gsi/releases/tag/2025-08-12)
* [Clover](https://github.com/Doze-off/Clover_treble/releases/tag/2025-07-28)
* [MistOS](https://github.com/Doze-off/MistOS_treble/releases/tag/2025-07-19)
* [WitAqua](https://github.com/Doze-off/WitAqua_treble/releases/tag/2025-07-01)
* [CherishOS](https://github.com/Doze-off/CherishOS_gsi/releases/tag/2025-08-10)
* [LunarisOS](https://github.com/Doze-off/Lunaris-AOSP_gsi/releases/tag/2025-08-11)

---

## 📦 Extract GSI

GSI ZIP ফাইলটি **7-Zip** ব্যবহার করে Extract করুন।

Extract করার পর আপনি `system.img` ফাইলটি পাবেন।

---

## ⚡ Flashing Commands

### 1. Fastboot Mode-এ Boot করুন

```bash
adb reboot bootloader
```


### 2. System Partition Check করুন

```bash
fastboot getvar current-slot
```
### 3. Fastboot-D Mode-এ যান

```bash
fastboot reboot fastboot
```

### 4. Dynamic Partition হলে

```bash
fastboot delete-logical-partition product_a
fastboot delete-logical-partition product_b
```
👉 অর্থাৎ,👉 **Active Slot অনুযায়ী Logical Partition Delete করতে হবে।**

👉 অর্থাৎ, প্রথমে `fastboot getvar current-slot` কমান্ডের মাধ্যমে আপনার ডিভাইসের **Active Slot** চেক করুন।

* যদি **Active Slot `a`** দেখায়, তাহলে ব্যবহার করুন:

```bash
fastboot delete-logical-partition product_a
```

* যদি **Active Slot `b`** দেখায়, তাহলে ব্যবহার করুন:

```bash
fastboot delete-logical-partition product_b
```

* আর যদি `fastboot getvar current-slot` কমান্ডে **কোনো নির্দিষ্ট slot (a/b) না দেখায়**, তাহলে দুটো কমান্ডই ব্যবহার করুন:

```bash
fastboot delete-logical-partition product_a
fastboot delete-logical-partition product_b
```


⚠️ **অর্থাৎ, active slot যেটা থাকবে সেই অনুযায়ী শুধু A অথবা B command ব্যবহার করবেন। কোনো নির্দিষ্ট slot না দেখালে A এবং B—দুটো command-ই ব্যবহার করবেন।**


### 5. GSI Flash করুন

Extract করা `system.img` ফাইলটি যে folder-এ আছে, সেই folder থেকে command চালান:

```bash
fastboot flash system system.img
```

### 6. Userdata Erase করুন

```bash
fastboot erase userdata
```

### 7. Recovery te Reboot করুন

```bash
fastboot reboot recovery
```
### 8. Format data /factory reset then Reboot system
Format data /factory reset then Reboot system
---

## ⚠️ MISCELLANEOUS

যদি GSI flash করার সময় নিচের error দেখতে পান:

```text
FAILED (remote: 'Not enough space to resize partition')
```

তাহলে নিচের logical partitions delete করে আবার GSI flash করার চেষ্টা করতে পারেন:

```bash
fastboot delete-logical-partition system_ext
```

```bash
fastboot delete-logical-partition system_ext_a
```

```bash
fastboot delete-logical-partition system_ext_b
```

```bash
fastboot delete-logical-partition product
```

```bash
fastboot delete-logical-partition product_a
```

```bash
fastboot delete-logical-partition product_b
```

এরপর আবার:

```bash
fastboot flash system system.img
```

---

## ⚠️ Important

GSI flash করার আগে আপনার ডিভাইস **Project Treble / Dynamic Partition** support করে কিনা নিশ্চিত করুন।

ভুল GSI বা ভুল partition command ব্যবহার করলে bootloop বা software-related সমস্যা হতে পারে। নিজের ডিভাইসের জন্য সঠিক GSI variant নির্বাচন করুন।

---

## 📱 Need Help?

তারপরও সমস্যা হলে Telegram-এ যোগাযোগ করতে পারেন:

**Telegram:** [@raquibulhasankafi](https://t.me/raquibulhasankafi)

---

### ❤️ Credits

**Guide by KAFI 777**

If this guide helped you, consider ⭐ starring the repository.
