# T430-BIOS-macOS
I needed cfg lock to be unlocked.

This is a lightly-tested patch to @n4ru's current T430.rom binary from https://github.com/n4ru/1vyrain via the .iso

Drop it on a non-SSL HTTP server near you and take option 2 when your T430 wakes up from sleep during the exploit.

It is patched to permanently to leave cfg lock open in PowerMgmtDxe / PowerManagement2 (PE32 image)

Using sudonull's method, I substitute HEX "75080FBAE80F" with "EB080FBAE80F" (JE becomes JMP) described in 2014. See https://sudonull.com/post/115796-UEFI-BIOS-Modification-Part-One-Introducing-UEFITool

Note: two implementations of ifrextract said "bad protocol." I used a hex editor.

SHA256SUM; 75beed69cb11ce5dcffa94ed7555e159df097d3b9fa1f89d926f8844682b4480

Thanks to: @jozews321 for his version and @n4ru for https://github.com/n4ru/1vyrain as well asl @5T33Z0 for his T530 EFI. And https://sudonull.com

Currently running https://github.com/5T33Z0/Lenovo-T530-Hackintosh-OpenCore on a T430  mostliy unmodified.

We have observed that W530.rom and T530.rom do not need this patch.

Cautionary Notes:

1. This breaks TXT (trusted execution) but that is supposed to be disabled anyway (by disabling the Security Chip).
2. You may stumble on an unknown case that bricks your hack.
