# Sultan Zumapro KSU Workflow

A high-performance, security-focused kernel for Pixel 9 series (zumapro), merging the stability of **Sultan Kernel** with advanced stealth and networking features.

## 🚀 Key Features
- **Stealth Core:** Dedicated **KowSU + SUSFS Mini** and **xxKSU + NoMount** variants.
- **Fortress Networking:** `atp4pixel` compatibility with BBR/BBRv3, IPSet, and XFRM/ESP support.
- **NoMount:** A kernel-based file injection and path redirection framework for Android kernels.
- **Hook Modes:** xxKSU syscall-table + LSM, full manual-hook, and ARM64 branch-link variants.

---

## 📦 Build Variants

| Variant | Description | Base Source |
| :--- | :--- | :--- |
| **KowSU-SUSFS** | Official Sultan base with manual KowSU/SUSFS bridging. | [Official Sultan](https://github.com/kerneltoast/android_kernel_google_tensynos) |
| **xxKSU-NoMount** | xxKSU with NoMount, available with standard or full manual hooks. | [Official Sultan](https://github.com/kerneltoast/android_kernel_google_tensynos) |
| **Sultan17-xxKSU-NoMount** | Android 17 source with full manual or ARM64 branch-link hooks; BBRv3 is enabled by default. | [ZQZCC/SULTAN17](https://github.com/ZQZCC/SULTAN17) |

---

## 🤝 Credits & Acknowledgments

This project is made possible thanks to the work of the following developers:

### 🛠️ Kernel & Core Logic
* **[Sultan (kerneltoast)](https://github.com/kerneltoast)** - For the exceptional Sultan Kernel base.
* **[Yapixel](https://github.com/yapixel)** - For kernel patches and specialized configuration logic.
* **[Google BBR](https://github.com/google/bbr)** & **[WildKernels](https://github.com/WildKernels/kernel_patches)** - For BBRv3 and its Android 6.1 KABI adaptation.

### 🛡️ Stealth & Security
* **[KernelSU Team](https://github.com/tiann/KernelSU)** - For the original KernelSU project.
* **[KOWX712](https://github.com/KOWX712)** & **[backslashxx](https://github.com/backslashxx)** - For specialized KernelSU integration methods.
* **[maxsteeel](https://github.com/maxsteeel/nomount)** - The creator of **NoMount**.
* **[simonpunk](https://gitlab.com/simonpunk/susfs4ksu)** - The creator of **SUSFS**.

### 🔧 Tools & Distribution
* **[TheWildJames](https://github.com/TheWildJames)** - AnyKernel3 distribution template.
* **[TheSillyOk](https://github.com/TheSillyOk)** - Build automation scripts.
