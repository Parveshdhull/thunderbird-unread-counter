# thunderbird-unread-counter 
 Display unread emails count in linux tray/panel for all added accounts

### Prerequisite:
- inotify-tools

### Known Issue:
This program uses `INBOX.msf` files for checking the unread emails count, for each IMAP account as shown in this [StackExchange answer](https://unix.stackexchange.com/a/486672).

But if several emails are received at once, (for example when thunderbird just started) then these `INBOX.msf` files returns the wrong count for unread emails.

Still, even when count is wrong it tells that there are some unread emails. Also if you want to disable counter completely and just want to use this as unread indicator, you can use `SHOW_COUNT=false`.
Also if you find any workaround this issue, please feel free to create a PR.

### Parameters:
- THUNDERBIRD_PROFILE_PATH - Path to thunderbird profile
- LAUNCHER_FILE - Create launcher file for thunderbird ([Steps]())
- SHOW_COUNT - Will Show unread count if true otherwise just a red dot to show new email

### Bonus TIP
For keeping thunderbird running in the background and emails synced
- Auto Start thunderbird on the system startup

- Install [Minimize on close](https://addons.thunderbird.net/en-us/thunderbird/addon/minimize-on-close/)

- Autorun `wmctrl -r "thunderbird" -b add,skip_taskbar,hidden` on startup.

  This way thunderbird will not be always visible in the taskbar and on Alt-tab. And you can keep using the PC while thunderbird running in the background without interfering. And it will open very fast on pressing launcher icon.

- Autorun `thunderbird-unread-counter` on startup: