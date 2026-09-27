# Quick Folder Terminal

Quick Folder Terminal is a Windows desktop app for opening Command Prompt, PowerShell, or Windows Terminal in the folder you are working in. It also lets you save commands—such as `npm start`—and run them in a chosen folder with one click.

## What it does

Choose a project folder, choose a terminal, then either open an interactive shell or click one of your saved commands. The shell starts in that folder and stays open after the command runs, so you can continue working or inspect its output.

The app runs locally. Your saved folders and commands are kept on this PC; they are not uploaded or synced by the app.

## Features

- **CMD, PowerShell, and Windows Terminal** — choose which terminal to open.
- **Start in a chosen folder** — browse for a folder, pick a recent or saved one, or open a folder from File Explorer.
- **Saved and recent folders** — pin frequently used folders and quickly revisit recent projects.
- **Saved commands** — save a friendly name and command, such as **Start app** / `npm start`, then click it to run in the selected folder and terminal. Commands are only run when clicked, and can be removed from the list.
- **Run as administrator** — turn on the administrator option when needed; Windows displays its permission prompt.
- **File Explorer menu** — after installing, right-click a folder or empty space inside a folder and choose **Open in Quick Folder Terminal**. The app opens with that folder selected; choose a terminal and click **Open terminal** or a saved command.
- **Keyboard shortcuts** — `Ctrl+K` opens the folder picker; `Ctrl+Enter` opens the selected terminal.

Saved commands are stored for the current Windows account. When you choose Windows Terminal for a saved command, the command runs in a PowerShell tab hosted by Windows Terminal.

## Install and run

### Installer

Run `release/Quick Folder Terminal Setup 1.6.0.exe` and follow the setup steps. The installer is per-user: it creates Start menu and desktop shortcuts and adds the File Explorer menu entries for your Windows account. Uninstalling the app removes those entries.

### Portable app

Run `release/Quick Folder Terminal 1.6.0.exe` directly. The portable app does not need installation. The File Explorer menu entries are added by the installer, so use the installer if you want that integration.

### Share the app on GitHub

Keep the source code in the repository and upload the built `.exe` files as **Release assets**. GitHub's browser-based repository upload is limited to 25 MiB per file, while these app builds are about 92 MB each. A GitHub Release supports individual assets up to 2 GiB, so both executables fit. See GitHub's docs for [repository uploads](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository) and [release limits](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases).

To publish version 1.6.0, push the source and README to your repository, open **Releases** → **Create a new release**, use the tag `v1.6.0`, attach `Quick Folder Terminal Setup 1.6.0.exe` and optionally `Quick Folder Terminal 1.6.0.exe` from the local `release/` folder, then publish. Other users can download the installer from that release instead of trying to upload the executable into the source repository.

### Use it

1. Choose a folder with **Choose a folder**, or open a folder in the app from File Explorer.
2. Select **Command Prompt**, **PowerShell**, or **Windows Terminal**.
3. To open a normal interactive shell, click **Open terminal**.
4. To save a command, select **Add command**, enter a display name and command, and select **Save command**. Later, select a folder and terminal, then click that saved command to run it.
5. Enable **Run as administrator** before opening the shell or clicking a saved command if it needs elevation.

## Personal installer shortcut

[Quick Folder Terminal Setup 1.6.0.lnk](<./Quick Folder Terminal Setup 1.6.0.lnk>) is a shortcut created on this PC. It points to `C:\Users\Game_ACC\OneDrive\Documents\ChatGPT\P2\release\Quick Folder Terminal Setup 1.6.0.exe`, so it will not work for someone whose files are installed in a different directory. Use the installer file above on another PC; setup will create shortcuts using that PC's own install location.

## Run from source

Install Node.js 22.12 or newer, then run these commands from the project folder:

```powershell
npm install
npm start
```

## Build the Windows executables

```powershell
npm install
npm run dist
```

This builds the installer and portable x64 app in `release/`. To build one package only:

```powershell
npm run dist:installer
npm run dist:portable
```
