# CNGMSPatch

A minimal Magisk module that only patches CN GMS regional restriction behavior.

## Principle

This module replaces `cn.google.services.xml` with an empty permissions definition.
On ROMs that enforce CN region limits through this file, replacing it can remove those limits.

## What this module changes

It provides the following files through Magisk Magic Mount:

- `system/product/etc/permissions/cn.google.services.xml`
- `system/system_ext/etc/permissions/cn.google.services.xml`
- `system/etc/permissions/cn.google.services.xml`

All three files contain the same empty `<permissions>` root.

## Notes

- This module only targets file-based restriction logic.
- If your ROM enforces restriction in framework code or server-side policy, effect may be partial.
- Reboot after installation.

## Build zip

From inside `CNGMSPatch` directory, zip all contents (not the folder itself) and install in Magisk/KernelSU/APatch.
