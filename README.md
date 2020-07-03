# Unpack
Unpack is a simple and ugly python script to handle multiple archives. 

Instead typing tar -xvzf /unzip/gzip etc you just need to know:
```
unpack
```
After unpack command, type the name of the target archive
```
unpack archive.tar
unpack archive.gz
unpack archive.zip
...
```
If archive has been successfully processed by unpack, it will create a decompressed directory/file in the same directory as target archive. 

So is it just bunch of decompression tools stitched into a python script? Pretty much yeah. However unpack has one additional feature: it repacks ugly archives.
## Ugly archives
"Ugly" archive is an archive which has more than one file/directory at the top level.

Ugly archive:
```
/foo
/foo2.xyz
/foo3.sth
```
Nice archive:
```
/dir/foo
/dir/foo2.xyz
/dir/foo3.sth
```

Whenever unpack detecs an ugly archive it creates a new top directory and extracts files there, instead of spilling them all over the place.

Unpack has only one option: -d (delete).

If you run the following:
```
unpack -d archive.tar
```
unpack will decompress files and then delete archive.tar

## Installation
Add unpack script to a folder that is on $PATH.

e.g. /usr/local/bin

## Supported archive formats
```
tar
zip
gz
7z
```
