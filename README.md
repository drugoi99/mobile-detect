MobileDetect
====================================================

### Description

MobileDetect is a simple python class imported from PHP for detecting mobile devices including tablets.

The package is imported from [MobileDetect](http://www.mobiledetect.net) which was originally written in PHP.

### Usage

Using the Flask framework as an example:

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    detect_mobile = DetectMobile()
    request.MOBILE = detect_mobile.is_mobile()
    request.MOBILE_DEVICE = detect_mobile.device
    request.MOBILE_OS = detect_mobile.os
    
    template = '/%sindex.html' % ('mobile/' if request.MOBILE else '')
    return render_template('index.html')
 
if __name__ == '__main__':
    app.run()
    
```
