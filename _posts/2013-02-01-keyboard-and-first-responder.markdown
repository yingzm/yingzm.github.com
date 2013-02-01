---
layout: post
title: Keyboard and first responder
category: iOS
---
{% include JB/setup %}

I came to a very strange problem today. I have a split layout view  for iPad. The master view is some control UI, the detail is a text view. In the master view, I use presentModalController to bring another view controller. The modal style for presenting the view controller is flip horizontal. 
Here is the strange thing. I have text view the first responder, and keyboard is shown. But then I brings up the modal view controller, the keyboard disappeared, but the text view still has first responder! Here is the strange thing. The text view can be selected, copy, paste, but can't show keyboard....

Still don't know why, maybe Apple don't want developer to do that.