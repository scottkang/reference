```python
$>python3
>>> import os
>>> print( os.stat("./install.log") );
os.stat_result(st_mode=33188, st_ino=124824341, st_dev=16777233, st_nlink=1, st_uid=501, st_gid=20, st_size=41579, st_atime=1715587823, st_mtime=1715587821, st_ctime=1715587821)
>>> atime = 200000000;
>>> mtime = 100000000
>>> path = "./install.log"
>>> tup = (atime, mtime)
>>> os.utime(path, tup)
>>> print( os.stat("./install.log") );
Ctrl-D
```
