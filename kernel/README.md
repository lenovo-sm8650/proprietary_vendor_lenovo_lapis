# Stock Lenovo kernel binaries

From the stock ZUI_17.5.10.362 firmware of the Lenovo Yoga Tab Plus (TB520FU).
The kernel itself is built from source (kernel/lenovo/TB520FU, Android common
kernel android14-6.1); these are the Lenovo/Qualcomm parts without matching
public source:

- `dtb/`, `dtbo.img` — device trees. The dtb comes from an installed
  vendor_boot whose region string was changed from ROW to PRC by LTBox.
- `modules/vendor_boot/`, `modules/vendor_dlkm/` — vendor kernel modules
  (unsigned; GKI loads them with MODULE_SIG_PROTECT) and their load lists.

Not managed by extract-files: a full extraction clears this repository, so
restore this directory with `git checkout -- kernel` afterwards.
