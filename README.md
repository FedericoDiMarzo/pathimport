

# pathimport #

This simple python module allows to elegantly handle relative imports on python.

### Why pathimport? ###
Using relative imports in python can lead to numerous headaches and subtle problems that require a deep understanding of how the interpreter loads other modules and scripts on runtime. This package wants to simplify the life of the typical python users, allowing them to import from other scripts of the same project effortlessly.
   
### Installation ###
The pathimport module can be installed through pip.
```
pip install pathimport
```

### Usage ###
Let's suppose to have a python project with the following structure.

	├── submodule_a                            
	│   ├── __init__.py 
	│   └── script_a.py                    
	├── submodule_b
	│   ├── __init__.py 
	│   └── script_b.py
	├── __init__.p
	└── common.py

Inside `common.py` we have defined the following function.
```python
def fun_common():
	# do things...
```

While in `script_a.py` we have defined the following.
```python
def fun_a():
	# do things...
```

To avoid the usage of relative imports, pathimport can be used to load these functions inside `script_b.py`.

```python
from pathimport import set_module_root
set_module_root("..")

# from now on all the imports can be
# perfomed from the module root
from common import fun_common
from submodule_a import fun_a

if __name__ == "__main__":
	fun_common()
	fun_a()
```

### Additional Resources ###
* [Stack Overflow question on relative imports](https://stackoverflow.com/questions/14132789/relative-imports-for-the-billionth-time)
