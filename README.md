# File Watcher

### Description
The class listens to the file system change notifications and raises events when a directory, or file in a directory, changes.  

### Example
```
fw                       TFileWatchManager    !- class instance
sFolderName              STRING(256), AUTO    !- folder to listen for changes
bIncludeChildren         BOOL, AUTO           !- listen for subdirs changes as well.
dwNotifyFilter           typFILE_NOTIFY, AUTO !- notifications.
sFileName                STRING(256), AUTO    !- file/dir name which raised an event.
dwAction                 typFILE_ACTION, AUTO !- notification action
  CODE

  !- Start listen to the folder.
  sFolderName = 'C:\path\to\folder'
  bIncludeChildren = TRUE
  dwNotifyFilter = FILE_NOTIFY_CHANGE_LAST_WRITE + FILE_NOTIFY_CHANGE_CREATION + FILE_NOTIFY_CHANGE_FILE_NAME
  fw.Run(sFolderName, bIncludeChildren, dwNotifyFilter)

  OPEN(Window)
  ACCEPT
    IF fw.TakeNotify(sFileName, dwAction)
      !- log the changes
      printd('%s: %s', sFileName, ExplainNotifyAction(dwAction))
    END
  END

  !- stop listening.
  fw.Terminate()
```

## Requirements
- Clarion 6.3 and newer.
- ABC and Legacy template chains.

## Price
$50 via [PayPal](https://www.paypal.me/mikeduglas?ppid=PPC000628&cnac=RU&rsta=ru_RU(ru_RU)&cust=8W29QJ6GKY9HS&unptid=75f96da6-24a4-11e9-ae2c-441ea14e9560&t=&cal=ff0291196b3f5&calc=ff0291196b3f5&calf=ff0291196b3f5&unp_tpcid=ppme-social-user-profile-created&page=main:email&pgrp=main:email&e=op&mchn=em&s=ci&mail=sys).  