# BBRv3 patch

The patches add BBRv3 as the separate `bbr3` TCP congestion-control algorithm
while retaining the kernel's existing BBR v1 and CUBIC implementations.

- `bbrv3-android14-6.1.patch`: Sultan Android 16 integration.
- `bbrv3-sultan17-6.1.patch`: regenerated against Ante0 `sultan-17`.

## Sources

- Algorithm reference: Google BBR `v3` at
  [`90210de4b779d40496dee0b89081780eeddf2a60`](https://github.com/google/bbr/commit/90210de4b779d40496dee0b89081780eeddf2a60).
- Android 6.1 KABI adaptation: WildKernels `android14-6.1` patch at
  [`3a75d651cf999e213c6998a7101eea7c5c6c741e`](https://github.com/WildKernels/kernel_patches/commit/3a75d651cf999e213c6998a7101eea7c5c6c741e).
- Integration base: Sultan `16.0.0-sultan` at
  [`ec1598e9008e7cc254b29cce4591889cfef388ae`](https://github.com/ZQZCC/android_kernel_google_tensynos/commit/ec1598e9008e7cc254b29cce4591889cfef388ae).
- Android 17 integration base: Ante0 `sultan-17`.

## Local safeguards

- Keep the 104-byte `icsk_ca_priv` layout unchanged for Android KABI.
- Allocate BBRv3's larger per-socket state dynamically.
- Fall back to Reno callbacks if that allocation fails instead of dereferencing
  a missing state object.
- Leave PLB disabled by default, matching the reference implementation.

The BBRv3 workflow enables `CONFIG_TCP_CONG_BBR3=y` and selects `bbr3` as the
default. Users can still select `bbr` or `cubic` at runtime.
