# Python Note

## Index
* [Path]
  * [Environment variable](#environment)
* [File](#file)
  * [Read and write file line by line](#read-and-write-file-line-by-line)
  * [Copy file](#copy-file)
***

## Path
### Environment variable
```python
import os
# linux user path
usr_path = os.path.expanduser('~')
# linux env variable path
shell_path = os.path.expandvars('$SHELL')
```

## File
## Read and write file line by line
```python
# read file using readlines()
in_file = open('in.txt', 'r')
in_file_lines = in_file.readlines()
# write file using writelines()
out_file = open('out.txt', 'w')
out_file_lines = out_file.writelines(in_file_lines)
```
## Copy file
```python
import shutil
src_file_name = 'src.txt'
dst_file_name = 'dst.txt'
shutil.copyfile(src_file_name, dst_file_name)
```