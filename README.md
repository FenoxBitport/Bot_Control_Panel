# BOT CONTROL PANEL
**Look after your bot from your desktop, without opening the hosting website.**
Made by **Fenox** from **Bitport**. Free and open source under the MIT License.

Works with any bot hosted on a **Pterodactyl** or **Pelican** hosting panel: Discord bots, Minecraft servers, game
servers, anything your host runs. Use one hosting site or several, and switch between them without logging out.

**Current version: 1.2.0** · [Download](https://github.com/FenoxBitport/Bot_Control_Panel/releases/latest) ·
[Report a bug](https://github.com/FenoxBitport/Bot_Control_Panel/issues)

---

## Download and install (Windows 10 and 11)

1. Open **[Releases](https://github.com/FenoxBitport/Bot_Control_Panel/releases/latest)** and download
   **`Bot-Control-Panel-Setup-1.2.0.exe`**.
2. Run it. It installs for your Windows user only (no admin rights needed), adds Desktop and Start-menu shortcuts,
   and opens the program.

> **"Windows protected your PC"?** That appears because the program isn't signed with a paid certificate.
> Click **More info**, then **Run anyway**. You only see it once.

**Updating:** run the newer Setup. Your saved hosting sites and settings are kept.
**Removing:** Windows Settings → Apps → Bot Control Panel → Uninstall.

## Getting started

1. **Hosting site address:** the address you open in your browser to manage your servers, for example
   `https://panel.yourhost.com`. The app checks it as you type and tells you whether it found a Pterodactyl or a
   Pelican panel. (A link to one server, like `https://panel.yourhost.com/server/abc12345`, opens that server first.)
2. **API key:** a key lets the app manage your servers without knowing your password.

   | Panel | Where to make the key | It starts with |
   |---|---|---|
   | Pterodactyl | **Account → API Credentials** | `ptlc_` |
   | Pelican | **Your profile → API Keys** | `pacc_` |

   Give it any description (like "Bot Control Panel"), leave *Allowed IPs* empty and copy the key.
   The login screen has an **Open it for me** link that takes you there.
3. Paste both in and click **Connect**. Tick **Remember this site** to stay logged in. The key is then saved
   encrypted, locked to your Windows account.

**More than one hosting site?** Click **+ Add another site** on the login screen for each one. Inside the app, the
**globe button** on the left switches between them without logging out. Each key is only ever sent to its own site.

## What you can do

- **Your servers:** every server with its status and live CPU, memory and disk, refreshed every few seconds.
- **Console:** see what your bot prints, live, and send it commands.
- **Start, Restart, Stop**, with uptime and usage bars.
- **Files:** edit your bot's code in a proper code editor. JavaScript and JSON mistakes are shown as you type, with
  a plain-English hint. After saving, press **Restart** so your bot uses the change.
  - When someone else changed a file, a yellow bar tells you, and **Show changes** shows exactly what they did.
  - Fold code blocks, and use the shortcuts you know: Ctrl+S save, Ctrl+/ comment, Ctrl+Shift+[ / ] fold.
- **Activity:** who changed what and when (files, start/stop, commands, settings), with a search box.
  A red number means something new happened.
- **Backups & users:** backups, and letting friends help with exactly the access you choose.
- **Server settings:** startup, databases, network (addresses and ports) and settings (rename, reinstall).
- **Your account:** password, two-step login, API keys, SSH keys and login history.
- **Make it yours:** 9 themes (code colors match VS Code), your own colors for the usage bars and accent, fonts,
  text size and line spacing.
- **What's new:** after each update a window shows what changed. Open it again any time with the ✨ button.

## Keeping it safe

**Your API key never reaches the app's window.** It stays in the protected part of the program and is only ever
sent to its own hosting site, over an encrypted connection. Redirects are refused, so it can't be forwarded anywhere.

**Everything the app saves is encrypted.** When the app is closed, its data folder holds only:
- `vault.dat`: your saved sites and keys, app lock and settings, encrypted with AES-256;
- `Local State`: that encryption key, itself locked to your Windows account.

The app's window keeps nothing on disk, and the browser engine's temporary files are removed when you close the app.
If the app ever can't open its encrypted file, it sets it aside instead of replacing it, so nothing is lost.

**Under Your account → Security:**
- **App lock:** ask for a 6-digit code from your phone (Google or Microsoft Authenticator) or your Discord each time
  the app opens, after you've left it alone for a while, and whenever Windows locks or the computer sleeps.
  Wrong codes pause it for longer each time, up to a day.
  Lost your phone? Click **Can't get a code?** on the lock screen. That removes the lock *and* your saved sites,
  so nobody can use them; you just paste your keys again.
- **Hide from screen sharing:** the window shows up black in screenshots, recordings and screen shares.
- **Saved hosting sites:** see them, or forget any of them.

**More protection built in:**
- The program is **sealed**: it checks its own files when it starts and won't run if they've been changed.
- No developer tools or debugging, and Electron's built-in backdoors are switched off inside the program file.
- A site can't freeze the app by sending an endless answer, and the address check can't be used to scan a network.
- Files with secrets, like `.env`, are never copied to your computer.
- Copied passwords, keys and codes are wiped from the clipboard after 30 seconds.
- While the app is locked, it holds no names of your sites or servers.

**What no app can stop:** someone who fully controls your Windows account (malware, a keylogger) can see what you
see. Keep Windows updated and don't run programs you don't trust. If Windows clipboard history (Win+V) is on, Windows
keeps its own copy of what you copy; turn it off in Settings → System → Clipboard if you copy passwords.
If your key ever leaks, delete it on your hosting site and make a new one.

## Sharing with friends

Send them the Setup `.exe` (or a link to the Releases page). They log in with their own API key. Your saved sites and
app lock live in your Windows profile, never in the program, so they're never shared.

## Something not working?

Click **Report bug** on the error message, or **Report a bug** in Help (the **?** button) or on the login screen.
A filled-in report opens here on GitHub, with private details (keys, links, IP addresses, emails, IDs) removed.
You need a GitHub account to post it, and nothing is sent until you press **Submit**.

---

**What's where**
- `app/main.js`, `app/preload.js`, `app/core/`: the protected part (keys, the encrypted vault, the app lock).
- `app/ui/`: the window.
- `app/build/`: build-only files, never shipped: the icon (`build/icon/make-icon.js` redraws it), the small launcher,
  the README that's installed with the app (`build/install/README.txt`), and `tidy-install.js`, which lays out the
  install folder:

```
Bot Control Panel\
  Bot Control Panel.exe              opens the program (a small launcher)
  Uninstall Bot Control Panel.exe
  README.txt, LICENSE.txt
  app\                               the program itself (sealed)
```

## License

MIT License, Copyright (c) 2026 Fenox (Bitport). You may use, change and share this program, as long as the copyright
notice and the license stay with it. See [`LICENSE`](LICENSE). Bundled libraries (CodeMirror, acorn) keep their own MIT
notices in `app/ui/vendor/THIRD-PARTY-LICENSES.txt`.
