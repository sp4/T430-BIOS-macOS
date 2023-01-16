# T430-BIOS-macOS
I needed cfg lock to be unlocked.

This is a lightly-tested patch to @n4ru's current T430.rom binary from https://github.com/n4ru/1vyrain via the .iso

It is patched to permanently leave cfg lock open in PowerMgmtDxe / PowerManagement2 (PE32_image)

Using sudonull's method,we  substitute "75080FBAE80F" with "EB080FBAE80F" (JE becomes JMP) described in 2014. See https://sudonull.com/post/115796-UEFI-BIOS-Modification-Part-One-Introducing-UEFITool

SHA256SUM; 75beed69cb11ce5dcffa94ed7555e159df097d3b9fa1f89d926f8844682b4480

Thanks to: @jozews321 for his version and @n4ru for https://github.com/n4ru/1vyrain as well asl @5T33Z0 for his T530 EFI.

Currently running https://github.com/5T33Z0/Lenovo-T530-Hackintosh-OpenCore on a T430  mostliy unmodified.

We have observed that W530.rom and T430.rom do not need tihs patch.
