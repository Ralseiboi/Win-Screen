# Build and install Win-Screen

This project includes a Windows notification listener for Discord alerts. It reads Discord's Windows notification feed; it does not use a Discord account token. The listener only reads notifications after you opt in from the app and approve Windows' access prompt. Discord notifications must be enabled in Windows and remain in the Windows notification feed for Win-Screen to mirror them.

## Build the installable package

1. Install Python 3.14 and the [Windows 10/11 SDK](https://developer.microsoft.com/windows/downloads/windows-sdk/) (including MakeAppx and SignTool).
2. Open PowerShell in this folder and run `./Build-Win-Screen-MSIX.ps1`.
3. Choose a password when prompted to protect the local signing key. The script creates `Win-Screen.msix` and `Win-Screen-Local.cer` in this folder.
4. Run `./Install-Win-Screen.ps1` from an elevated PowerShell window. It adds the local signing certificate to the machine's Trusted People store and installs Win-Screen.
5. Launch Win-Screen from Start. Open Notifications, select **Enable Discord notifications**, and approve the Windows prompt.
