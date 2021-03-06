---
layout: post
title: iOS keyboard notifications
category: ios
---
{% include JB/setup %}

iOS keyboard notification contains three notifications related to position:
* UIKeyboardWillShowNotification
* UIKeyboardWillHideNotification
* UIKeyboardWillChangeNotification

In different situations the notifications are different

* No keyboard, tap on text view to show keyboard.
1. change. From 0,748,1024,352 to 0,396,1024,352
2. show. From 0,748,1024,352 to 0,396,1024,352

* Keyboard is shown, click hide button to hide
** change. From 0,396,1024,352 to 0,748,1024,352
** hide. From 0,396,1024,352 to 0,748,1024,352

* Keyboard is shown, rotate from landscape to portrait
** change. From 0,396,1024,352 to 0,748,1024,352
** hide. From 0,396,1024,352 to 0,748,1024,352
** change. From 0,740,768,264 to 0,740,768,264
** show. From 0,1004,768,264 to 0,748,768,264

* Keyboard is shown, connect Bluetooth keyboard
** change.
** hide.

* Keyboard is hide, disconnect Bluetooth keyboard
** change.
** show

* Keyboard is shown, click undock
** change. From 0,396,1024,352 to 0,748,1024,352
** hide. From 0,396,1024,352 to 0,748,1024,352

* Keyboard is undock, click hide
** change. From 0,196,1024,353 to 0,748,1024,352

* Keyboard is undock and hide, tap on text view
** change. From 0,748,1024,352 to 0,196,1024,352

* Keyboard is undock and shown, click dock
** change. From 0,196,1024,352 to 0,396,1024,352
** show. From 0,748,1024,352 to 0,396,1024,352

* Keyboard is dock and shown, click split
** change. From 0,342,1024,406 to 0,748,1024,406
** hide. From 0,342,1024,406 to 0,748,124,406

* Keyboard is split and shown, switch to Chinese.
** change. From 0,332,1024,216 to 0,332,1024,216

* Keyboard is split and shown, click dock and merge
** change. From 0,278,1024,270 to 1024,-20,0,0
** change From 0,210,1024,486 to 0,342,1024,486
** show. From 0,748,1024,486 to 0,342,1024,486

OK, enough for the experiments. It is impossible to handle undock and split because for these two cases, the keyboard is invisible.

That let us have only one way: using inputAccessoryView. We let the system do most the work until a Bluetooth keyboard is attached. Now we don't set inputAccessoryView to nil directly. We change the content of inputAccessoryView.

In such way, we don't have to care about the complexity of attaching input accessory view. The only thing we need to care about it when Bluetooch keyboard is connected, we need to hide the keyboard.
