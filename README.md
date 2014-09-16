pyv4l2
=======

Python bindings for Video4Linux2 API

## example code
```python
import v4l2
cap = v4l2.Capture("/video/dev0")
frame = cap.get_frame()
cap = None
```


## building
python setup.py build_ext -i
