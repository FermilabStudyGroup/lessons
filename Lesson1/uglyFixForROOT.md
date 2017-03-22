It's very likely that most of the Macs will show this message when testing an Anaconda ROOT install.

```
dyld: Symbol not found: __cg_png_create_info_struct
  Referenced from: /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
  Expected in: /Users/sdporzio/anaconda2/envs/py2/lib/libPng.dylib
 in /System/Library/Frameworks/ImageIO.framework/Versions/A/ImageIO
```

I don't understand the problem very well, but I've found a temporary (ugly) fix. It looks like ROOT is not setting correctly the dynamic libraries (there's also a problem with Apple requesting libJPEG.dyld, and finding for some reason /opt/local/lib/libjpeg.dyld because the search is case insensitive).

In your Anaconda directory go to:

```
cd envs/py2/bin/
```

and then:

```
source thisroot.sh 
```

This won't solve the issue, you also have to now unset your `$DYLD_LIBRARY_PATH`, with:

```
unset DYLD_LIBRARY_PATH
```

ROOT will still won't work, but if you do:

```
ipython
import ROOT
```

It should work.

As I said, this is ugly, but it will let us through the tutorials for now.
