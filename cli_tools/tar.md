# Compressing and decompressing files

compress to myarchive.tgz:
```sh
tar -zcvf myarchive.tgz myfile.txt myotherfolder
```

decompress (will put all files/folders in same directory, overwriting):
tar -zxvf myarchive.tgz
