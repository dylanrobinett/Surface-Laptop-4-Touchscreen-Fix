
# Surface Laptop 4 Touchscreen Fix

Instructions for getting the touchscreen working on a Surface Laptop 4 running Ubuntu with Xorg.

## Prerequisites

- Make sure you are running Ubuntu with Xorg as the display server.

## How to Switch to Xorg

1. Log out of your current session.
2. On the login screen, click on the settings (gear) icon in the bottom-right corner.
3. Select "Ubuntu on Xorg" from the menu.
4. Log back in to your session.

## Steps to Enable the Touchscreen

1. **Download the Necessary Files:**
   - Ensure you have the following files downloaded to your system:
     - `linux-headers-6.8.6-surface-1_6.8.6-surface-1_amd64.deb`
     - `linux-image-6.8.6-surface-1_6.8.6-surface-1_amd64.deb`
   - These files are specific to the Surface Laptop 4 and are designed to work with the Linux-Surface kernel.

2. **Install the Kernel Image and Headers:**
   - Open a terminal.
   - Navigate to the directory where the downloaded `.deb` files are located. If they are in the `Downloads` directory, use the following command:
     ```bash
     cd ~/Downloads
     ```
   - Install the kernel image and headers by running:
     ```bash
     sudo dpkg -i linux-image-*.deb linux-headers-*.deb
     ```
   - This command installs both the image and headers required for the Surface-specific kernel.

3. **Reboot the System:**
   - After installation is complete, reboot your system to apply the new kernel:
     ```bash
     sudo reboot
     ```

## Note

After rebooting, your touchscreen should be fully functional. If it isn’t, make sure you’re running the correct kernel by checking with `uname -r` and verifying it shows `6.8.6-surface-1`.

