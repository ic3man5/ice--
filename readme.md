#ice Library
This is a very simple class to make dynamic library loads simple and easy. This code should multi-platform. The library gets automatically cleaned up and ice::Exception is thrown when an error occurs.

###Example Code
```
#include "ice.h"

try
{
    ice::Library lib("foo");
    ice::Function<int (int, int)> func(&lib, "foofunc");
    int i = func(2, 5);
}
catch (ice::Exception& ex)
{
    // ex.whatString() will look similar to this:
    // Failed to Retrieve address of function 'foofunc': Windows Error #0 for 'foo'
}

// lib and func auto clean up when they go out of scope

```

###License
The MIT License (MIT)

Copyright (c) <2015> <David Rebbe>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.