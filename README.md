# check if backups are enabled
adb shell bmgr enabled

# list all transporters available for backup
adb shell bmgr list transports

# backup
adb shell bmgr backupnow com.googlecodelabs.example.backupexample

# see all backup information
adb shell dumpsys backup

# get token to restore the backup
adb shell dumpsys backup | grep "com.googlecodelabs.example.backupexample" -A 4 | grep Current

# restore backup
adb shell bmgr restore $token com.googlecodelabs.example.backupexample
