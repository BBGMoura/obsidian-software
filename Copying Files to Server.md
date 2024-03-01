SCP (secure copy) is a command-line utility thar allows you to securely copy files and directories between locations.

```sh
scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2
```
- `OPTION` - [scp options](https://linux.die.net/man/1/scp) such as cipher, ssh configuration, ssh port, limit, recursive copy …etc.
-  `[user@]SRC_HOST:]file1` - Source file.
-  `[user@]DEST_HOST:]file2` - Destination file

Local files can be specified using an absolute or relative path. Remote file names should include a user and host specification.

Example for localhost:
```
scp CorvusPay.p12 vagrant:     
```

Example for skywarp server:
```
 scp CorvusPay.p12 brunam@skywarp:/etc/fsbtech/corvuspay   
```

This copies the file from pwd to skywarp. (this doesnt work as we need to use the landing zone).