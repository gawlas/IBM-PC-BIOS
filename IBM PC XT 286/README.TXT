IBM PC XT 286 BIOS dated 04/21/86 based on the BIOS listings in the IBM PC XT 286 Technical Reference dated August 1986.
The BIOS was originally built using IBM MASM 2.0.

Notes:
- FILL.ASM was added to properly link the BIOS, this defines the area between the end of the main BIOS code and the ORGS data at E000.
- IAPX286.INC was derived based upon the generated code in the listings.
- The code at FF5A in ORGS.ASM is hidden from the BIOS listings with .XLIST.

Additional files:
FILL.ASM - see above
XT286LNK - linker response file
EXE2BIN - DEBUG script to convert the EXE file to a BIN file

Steps to build the PC XT 286 BIOS:
for %a in (*.asm) do masm %a;
link @xt286lnk
debug < exe2bin
