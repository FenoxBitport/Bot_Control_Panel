# BOT CONTROL PANEL
Look after your bot from your desktop, without opening the hosting
website. Works with any bot hosted on a Pterodactyl hosting panel.


GETTING STARTED
---------------
1. Open "Bot Control Panel" from your Desktop or the Start menu.
2. Hosting site link: the address of your hosting panel, for example
   https://panel.yourhost.com
   (A link to one server, like https://panel.yourhost.com/server/abc12345,
   opens that server first.)
3. API key: on your hosting site, go to Account > API Credentials, create
   a key (description "Bot Control Panel", leave Allowed IPs empty) and
   copy it. It starts with ptlc_
4. Paste both in and click Connect. Tick "Remember me" to stay logged in.
   Your key is then saved encrypted, locked to your Windows account.

Windows may say "Windows protected your PC" the first time you install.
Click "More info", then "Run anyway". That's normal for programs that
aren't signed with a paid certificate.


WHAT YOU CAN DO
---------------
- Console: see what your bot prints, and send it commands.
- Start, Restart, Stop, and live CPU, memory, disk and uptime.
- Files: edit your bot's code. After saving, press Restart so your bot
  uses the change. Mistakes in JavaScript and JSON are shown as you type.
- Activity: see who changed what, and when. Search it with the search box.
- Backups, Users, Startup, Databases, Network and Settings, just like on
  the hosting site.
- Your account (person icon): password, two-step login, API keys and
  login history.
- Theme (palette icon): colors, fonts and text size.
- Update (sparkle icon): see what changed in each version.


KEEPING IT SAFE
---------------
- Your API key works like a password. Don't share it. If it leaks, delete
  it on your hosting site (Account > API Credentials) and make a new one.
- App lock (Your account > Security): ask for a 6-digit code from your
  phone or your Discord each time the program opens, after it's left
  alone, and when Windows locks or the computer sleeps.
- Lost your phone? Click "Can't get a code?" on the lock screen. This
  removes the lock AND your saved login, so you'll paste your key again.
- Your key is only ever sent to your hosting site, over a secure
  connection. Nothing else leaves your computer, except bug reports you
  choose to send.


SOMETHING NOT WORKING?
----------------------
Click "Report bug" on the error message, or "Report a bug" in Help (the ?
icon) or on the login screen. A filled-in report opens on GitHub in your
browser, with private details removed. You need a GitHub account to post
it. Nothing is sent until you press Submit.

Bug reports:  https://github.com/FenoxBitport/Bot_Control_Panel/issues


UPDATING AND REMOVING
---------------------
- To update, run the new "Bot-Control-Panel-Setup" file. Your saved login
  and settings are kept.
- To remove the program, use "Uninstall Bot Control Panel.exe" in this
  folder, or Windows Settings > Apps. Your saved login and settings stay
  in your Windows profile, in case you install it again.


LICENSE
-------
Free to use and share under the MIT License. See LICENSE.txt.
Copyright (c) 2026 Fenox (Bitport)
