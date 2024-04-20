# Resetting passwords in Ubuntu

1. Shut down the machine
2. Spam the shift key when you see 'Press ESC for boot menu'
3. Press 'e'
4. Find the line that starts with the word 'linux'
5. Look for 'ro' and change it to 'rw init=/bin/sh'
6. Press F10
7. Let the machine boot into a shell
8. Enter 'passwd root'
9. Give the root account a new password
10. Shut down the VM from Proxmox
11. Reboot the VM
12. Enter the new login credentials

# Resetting passwords in Rocky

1. Shut down the machine
2. Spam the shift key when you see 'Press ESC for boot menu'
3. Press 'e'
4. Find the line that starts with the word 'linux' it should also end with 'quiet'
5. Add 'rd.break enforcing=0' to the end of the line
6. Press 'Ctrl-x'
7. Let the machine boot into a shell
8. Enter 'mount -o rw,remount /sysroot'
9. Enter 'chroot /sysroot'
10. Enter 'passwd root'
11. Give the root account a new password
12. Enter 'touch /.autorelabel
13. Enter 'exit'
14. Enter 'exit' again
15. Wait for the relabled process to finish and the machine will boot on its own
16. Enter the new login credentials

# Resetting passwords in Cent OS 7

1. Shut down the machine
2. Spam the shift key when you see 'Press ESC for boot menu'
3. Press 'e'
4. Find the line that starts with the word 'linux'
5. Look for 'ro' and change it to 'rw init=/sysroot/bin/sh'
6. Press 'Ctrl-x'
7. Let the machine boot into a shell
8. Enter 'chroot /sysroot'
9. Enter 'passwd root'
10. Give the root account a new password
11. Enter 'touch /.autorelabel
12. Enter 'exit'
13. Enter reboot
14. Wait for the relabled process to finish and the machine will boot on its own
15. Enter the new login credentials