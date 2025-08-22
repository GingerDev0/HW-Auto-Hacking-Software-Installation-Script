# HW Auto Hacking & Software Installation Script

## Overview
This Tampermonkey userscript automates hacking and software installation tasks on [Hacker Wars](https://hackerwars.io/). It scans the `/list` page for vulnerable IPs, hacks them using brute-force, uploads and installs specified software, clears logs, logs out, and repeats the process. The script includes features like a toggle button, IP skipping, root login detection with Discord notifications, and sniffed IP management.

## Features
- **Automation**: Automatically scans `/list` for IPs with no virus or not running the specified software, hacks them, uploads/installs software, clears logs, and logs out.
- **Toggle Control**: Sidebar button to start/stop automation.
- **IP Management**:
  - Skips IPs that return a cracker error or are user-specified.
  - Tracks processed IPs to avoid re-hacking.
  - Sniffs IPs from logs, excluding the user's own IP.
- **Software Check**: Verifies the software table before uploading to avoid redundant actions.
- **Root Login Alerts**: Checks `/logs` on load and every 3 seconds for root login attempts, pauses automation, saves IPs, and sends Discord webhook notifications with @mentions.
- **Discord Notifications**: Sends embedded messages with UK-formatted timestamps (DD/MM/YYYY HH:mm:ss) to a hardcoded, encrypted webhook URL with anti-spam measures.
- **Modals**:
  - Software configuration modal to select software.
  - Skipped IPs modal to manage IPs to avoid.
  - Sniffed IPs modal to view and save parsed IPs.
  - Disk space and virus type error modals.
  - End-of-list modal to restart or stop automation.
  - Log edit success modal.
- **Settings**: Allows setting Discord User ID for @mentions.

## Installation
1. Install [Tampermonkey](https://www.tampermonkey.net/) in your browser.
2. Copy the script from `==UserScript==.txt` and add it as a new script in Tampermonkey.
3. Save and ensure the script is enabled.

## Usage
1. **Set Software**:
   - Navigate to the sidebar and click "Set Software."
   - Select your desired software from the dropdown and save.
2. **Configure Discord Notifications**:
   - Click "Set Discord User ID" in the sidebar.
   - Enable Developer Mode in Discord, right-click your username, select "Copy ID," and paste it into the input field.
   - Save to enable @mentions in notifications (leave empty to disable).
3. **Start Automation**:
   - Click "HW Auto Hacking: Start" in the sidebar to begin scanning `/list`.
   - The script will hack IPs, upload/install software, clear logs, and log out.
4. **Manage IPs**:
   - Use "Add Skipped IP" to manually skip specific IPs.
   - Check "Sniffed IPs" to view IPs parsed from logs and save them to a `.txt` file.
5. **Root Login Alerts**:
   - The script monitors `/logs` for root login attempts, pauses automation, and sends Discord notifications.
6. **Pause/Resume**:
   - Toggle "HW Auto Hacking: Stop" to pause; toggle "Start" to resume.
7. **End of List**:
   - When no targets are found on the last page, a modal prompts to restart or stop.

## Requirements
- Browser with Tampermonkey installed.
- Access to [Hacker Wars](https://hackerwars.io/).
- A Discord User ID for notifications (optional).
- jQuery (loaded by the website, not bundled).

## Notes
- The Discord webhook URL is hardcoded and encrypted for security.
- The script uses `localStorage` to store settings, skipped IPs, processed IPs, and sniffed IPs.
- Ensure you have a cracker installed on Hacker Wars for brute-force hacking.
- The script skips IPs with insufficient cracker strength or disk space errors, adding them to the skipped list.

## License
This project is licensed under the MIT License. See the script header for details.

## Contributing
Suggestions and improvements are welcome! Feel free to open issues or submit pull requests on GitHub.

## Author
Developed by GingerDev, a Hacker Wars player. Feedback and ideas are appreciated!
