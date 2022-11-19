# Use `sfdisk` to Backup JSON Partition Tables

One cool thing about `sfdisk` is exporting a partition table to JSON.

```
sfdisk /dev/sda -J
```

```out
{
   "partitiontable": {
      "label":"dos",
      "id":"0x00000000",
      "device":"/dev/sda",
      "unit":"sectors",
      "sectorsize":512,
      "partitions": [
         {"node":"/dev/sda1", "start":32, "size":61341664, "type":"c"}
      ]
   }
}
```
