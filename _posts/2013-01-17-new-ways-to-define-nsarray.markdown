---
layout: post
title: New way to define NSArray
category: ios
---
{% include JB/setup %}

Generally we define NSArray as

    [NSArray arrayWithObjects:object0, object1, object2, nil]

However, it is also possible to define as

    @[object0, object1, object2]

Furthermore, we generally define number object like

    [NSNumber numberWithFloat:0.0f]

We can use

    @0.0f

More information about this objective-c literals, refer to [WWDC 2012](http://developer.apple.com/videos/wwdc/2012/) or [clans doc](http://clang.llvm.org/docs/ObjectiveCLiterals.html)
