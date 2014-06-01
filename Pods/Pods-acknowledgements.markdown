# Acknowledgements
This application makes use of the following third party libraries:

## NJKScrollFullScreen

The MIT License (MIT)

Copyright (c) 2013 Satoshi Asano

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

## SWTableViewCell

Copyright (c) 2013 Christopher Wendel

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

## SuProgress

Pronounced “Super Ogress” (as in a female Ogre who is also a super-hero),
SuProgress is a utlitity library to show a iOS-7-Safari-style progress bar under
the UINavigationBar for your app.

SuProgress is an easy to user, drop-in library for common progress types eg. NSURLConnection, UIWebView, and AFNetworking’s AFHTTPRequestOperation.

![gif](http://mobilemakersacademy.github.com/SuProgress/SuProgress.gif)

SuProgress was made by [Mobile Makers][mm], Chicago, an eight week intense
learning experience that will take you from beginner to professional iOS
developer.

SuProgress was mostly authored by [Max Howell][mxcl], a splendid chap.

Usage
-----
SuProgress is super easy to use:

```objc
[viewController SuProgressURLConnectionsCreatedInBlock:^{
	[NSURLConnection connectionWithRequest:request delegate:self];
}];
```

Any NSURLConnections created in that block have their progress proxied to the
SuProgressBarView, which we also create and maintain for you.

Of course this means **any** frameworks or methods you call that operate via
NSURLConnection will have their progress proxied. For example, the Facebook SDK:

```objc
[viewController SuProgressURLConnectionsCreatedInBlock:^{
	[FBRequestConnection startWithGraphPath:@"/me" completionHandler:foo];
}];
```

Neat, right?

Here’s how to display progress for a UIWebView:

```objc
[viewController SuProgressForWebView:webView]
```

And AFNetworking:

```objc
[viewController SuProgressForAFHTTPRequestOperation:operation];
```

Installation
------------
* Via [CocoaPods](http://cocoapods.org): `pod 'SuProgress'`;
* ***Or***, just copy `SuProgress.h` and `SuProgress.m` into your project

Caveats
-------
Currently we cannot handle NSURLConnections initialized via 
`sendAsynchronousRequest:queue:completionHandler:`. Please help us fix this!

TODO
----
Typically you need a progress meter for a multi-stage operation, eg. load
Facebook data for a user, then load data based on that. SuProgress isn't much
use for this eventuality yet, but it wouldn't be too hard to write a bit more
API which says: divide the bar into three sections, etc.

We plan to make `SuProgress` monitors for `NSProgress`, `NSOperationQueue`, pull
requests for any progress type welcome.

Issues
------
* The progress bar is anchored to the navigationbar so when you push a new controller onto that UINavigationController's stack, the SuProgressBarView will still be visible during and after the transition. Currently I am not sure of a good solution, so haven't fixed it.

Requirements
------------
* ARC
* iOS >= 6 (probably 7 currently, please fork and fix)

Example.xcodeproj
-----------------
The example only builds with Xcode 5.

License
=======
Copyright 2013, Max Howell, all rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

[mm]:http://mobilemakers.co
[mxcl]:http://mxcl.github.io

Generated by CocoaPods - http://cocoapods.org
