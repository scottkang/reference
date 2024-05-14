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
Example
$>python3 change_file_mtime.py install.log '2024-01-01 01:23:45'
```python
import os
import sys
import datetime
import sys

path = sys.argv[1]
target = sys.argv[2]

# date_str = '2023-02-28 14:30:00'
date_format = '%Y-%m-%d %H:%M:%S'
date_obj = datetime.datetime.strptime(target, date_format)
print( os.stat(path) );
timestamp = int(date_obj.timestamp())
atime = timestamp
mtime = timestamp
tup = (atime, mtime)
os.utime(path, tup)
print( os.stat(path) );
```

$>pip3 install pyinstaller

$>pyinstaller --onefile change_file_mtime.py
