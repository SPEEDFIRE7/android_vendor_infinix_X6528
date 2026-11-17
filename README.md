# Infinix Hot 40i (X6528) — vendor tree

Vendor makefiles for the **Infinix Hot 40i X6528 / X6528B** (Unisoc T606 /
UMS9230), for use with the LineageOS 20 device tree at `device/infinix/X6528`.

Generated from the stock X6528 dump with the same layout as the Smart 8
(X6525) reference vendor tree.

## Blobs are not in this repository

`proprietary/` is git-ignored. Only the generated makefiles are tracked here;
the binaries are extracted from your own stock dump.

Generated files that are tracked:

```
Android.bp                  # Soong prebuilt modules
Android.mk                  # legacy make glue
BoardConfigVendor.mk        # board flags (required by BoardConfig.mk)
X6528-vendor.mk             # PRODUCT_COPY_FILES / product packages
```

## Setting up

From the root of a LineageOS 20 source tree:

```bash
git clone <device-tree-url> -b lineage-20 device/infinix/X6528
git clone <vendor-tree-url> -b lineage-20 vendor/infinix/X6528

# Extract from your dump (writes vendor/infinix/X6528/proprietary/):
device/infinix/X6528/extract-files.sh /path/to/x6528-dump
```

Alternatively, unpack the supplied `infinix_X6528_vendor_blobs.zip` at the
root of the source tree — it already contains `vendor/infinix/X6528/proprietary/`.

## Building

```bash
source build/envsetup.sh
lunch lineage_X6528-userdebug
mka bacon
```

Blob licensing: these files are proprietary to Infinix/Transsion/Unisoc. Use
them only on hardware you own.
