# Write an ISO image into USB memory

## Check Device Name of USB Memory
### Command
```
lsblk
```

### Output Example
```
NAME        SIZE TYPE MOUNTPOINTS
sda       500G   disk
├─sda1      1G   part /boot
└─sda2    499G   part /
sdb        16G   disk
└─sdb1     16G   part /run/media/user/USB
```

この例ではUSBメモリは /dev/sdb です。 書き込み先にはパーティション（例：/dev/sdb1）ではなく、 デバイス全体（例：/dev/sdb）を指定します。

## Unmount USB Memory Partition
Unmount the USB memory partition if it is mounted automatically.
```
sudo umount /dev/sdb1
```


## Write the ISO Image
> ![TIP]
> Output File is `/dev/sdb`, NOT `/dev/sdb1`
```
sudo dd if=<full path of the iso file> of=/dev/sdb bs=4M status=progress conv=fsync
```

| Option | Explanation |
| --- | --- |
| if | Input File(ISO image) |
| of | Output File(USB memory) |
| bs=4M | Block size of writing |
| status=progress | Show progress |
| conv=fsync | Sync after writing |

## Sync Writing
```
sync
```

## Eject USB Memory
```
sudo eject /dev/sdb
```

