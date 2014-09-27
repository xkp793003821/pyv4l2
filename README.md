pyv4l2
=======

Python bindings for Video4Linux2 API using libjpegturbo (utilizing the tubojpeg api).

Full access to all uvc settings.
Enumerate all capture devices wiht list_devices()

Capture instance will always grab mjpeg conpressed frames from cameras.

Image data is returned as `Frame` object. This object will decompress and convert on the fly when image data is requested.
This gives the user the full flexiblity: Grab just the jpeg buffers or have them converted to YUV or Gray or RGB and only when you need.

The `Frame` class has caching build in to avoid double decompression or conversion.


## example code
```python
import v4l2
cap = v4l2.Capture("/video/dev0")
frame = cap.get_frame()
cap = None
```


##dependecy libjpeg-turbo 
Needs to be build with fpic!
Will be installed to `/opt/libjpeg-turbo`.

```
wget latest source
unzip source_dir
cd source_dir
./configure --with-pic
sudo make install
```

## just build locally
```
python setup.py build_ext -i
```

## or install system wide
```
python setup.py install
```
