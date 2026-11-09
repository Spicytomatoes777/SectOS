# SectOS
A tiny OS fit in 248 bytes made by Claude.

## Commands
1. "l" - shows the files made. There can be 16 files maximum.
2. "t X" - reads the insides of X, and displays it.
3. "n X" - makes a file with the name of X. If you type whatever in X, then press ESC, it makes the file with those selected insides. the name of files can be 12 characters long, maximum. Enter does not save the file, but it does start a new line.
4. "d X" - deletes the file of X.

# Removed features
The goal was to fit the OS into under 255 bytes, but because of this limit, claude had to remove the following:
1. The "> " (cannot know if the OS has started)
2. The Backspace key (if you make a file called ab, backspace, c, it will be shown ac in "l ac", but "t ac" or "d ac"  does nothing.)
3. The DS/ES/SS setup (the BIOS has to give zeroed segment registers, which some real machines don't)

# How to run (Windows)
To run the OS, you use QEMU, or Bochs. Claude has not tested other emulators, as their BIOS would make it too risky. Real hardware can be used, too, however, make sure it's BIOS gives zeroed segment registers, as there is no DS/ES/SS setup. Downloads for QEMU can be found at [QEMU's download page.](https://www.qemu.org/download/) Downloads for Bochs can be found at [Bochs's SourceForge page.](https://sourceforge.net/projects/bochs/files/bochs/)

## Using QEMU
1. Download the .img file
2. Go to whatever directory you installed QEMU at.
3. Put the .img file in 
4. Right click, and select "Open in Terminal."
5. Wait for everything to finish loading and copy and paste this into the terminal: .\qemu-system-i386 -drive format=raw,file=(name of disk, should be disk).img,if=floppy
6. Enjoy!

## Using Bochs
1. Download the .img file and the .txt file
2. Edit the .txt file to fit your installation preferences
3. Go to whatever directory you installed Bochs at.
4. Put both the .img and .txt files in
5. Right click, and select "Open in Terminal."
6. Wait for everything to finish loading and copy and paste this into the terminal: bochs -q -f bochsrc.txt
7. Enjoy!
