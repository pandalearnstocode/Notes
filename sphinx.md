
```shell
conda create --sphinx myenvy
conda activate sphinx
pip3 install sphinx sphinx-autoapi
git clone https://github.com/avcourt/spamfilter-py.git
tree -L 3
mkdir docs
cd docs
sphinx-quickstart
tree
vim conf.py
```

  
  

```python
# inital code
# import os
# import sys
# sys.path.insert(0, os.path.abspath('.'))
```

  

```python
# Changed code
import os
import sys
sys.path.insert(0, os.path.abspath('..'))
```

  
  
  

```shell
# shpinx-apidoc -o . ..
# make html
sphinx-build -b html . _build
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzczMDk5ODkwXX0=
-->