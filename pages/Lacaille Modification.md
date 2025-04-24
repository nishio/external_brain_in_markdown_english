---
title: "Lacaille Modification"
---

I have a lot of things I want to try for myself [[Lacaille]] modification

- The original [https://lacaille.jpn.org/](https://lacaille.jpn.org/)
    - GPL
- Forked from here [https://github.com/ikesato/Lacaille](https://github.com/ikesato/Lacaille)
    - 2.2.2
    - [[Counting Back Space in Lacaille]] : v1 v2
- Merged 2.3 of the original: v3

    - [[I want to type round brackets and braces at home position.]]
    - Done: [[Use two different shifts even in English mode.]]

    - [[I want to input Unicode symbols.]]
        - [[Modified Lacaille keymap to JSON]]
        - [[🤔Key]]

---
objc

```
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:0]), @"No shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:1]), @"With left shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:2]), @"With right shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:3]), @"With outer shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:4]), @"ASCII - No shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:5]), @"ASCII - With outer shift",
convTraditionalKeyData([(ViewDataModel *)obj getKeyData:6]), @"With modifier key",
```


objc

```
enum {
    KANA_NO_SHIFT,
    KANA_L_THUMB,
    KANA_R_THUMB,
    KANA_OUTER_SHIFT,
    ASCII_NO_SHIFT,
    ASCII_OUTER_SHIFT,
    WITH_MODIFIER,
    ASCII_L_THUMB,
    ASCII_R_THUMB
};
```


objc

```
static CGKeyCode viewTable[] = {
    6, 7, 8, 9, 11, 45, 46, 43, 47, 44, LAYOUT_KEY_COUNT - 1,   // 94
    0, 1, 2, 3, 5, 4, 38, 40, 37, 41, 39, 42,
    12, 13, 14, 15, 17, 16, 32, 34, 31, 35, 33, 30,
    18, 19, 20, 21, 23, 22, 26, 28, 25, 29, 27, 24, LAYOUT_KEY_COUNT - 2   // 93
};
```

This is a letter key written from the bottom
94: kVK_JIS_Underscore
93: kVK_JIS_Yen: 0x5D
see [[kVK_JIS]]

objc

```
static inline void startTimer(NSTimeInterval negativeInterval) {
    [gLock lock];
    [gTimer invalidate];
    NSTimeInterval interval = prefTwait - negativeInterval;
    gTimer = [NSTimer scheduledTimerWithTimeInterval:(interval >= 0 ? interval : 0)
                                              target:self_
                                            selector:@selector(timerFired:)
                                            userInfo:(__bridge id)nil
                                             repeats:NO];
    [gLock unlock];
}

static inline void fireTimer() {
    [gTimer invalidate];
    [self_ timerFired:nil];
}
```


indicates object of desire, like, hate, etc.
[[getKeyDataForOya]] Keycode=0, oya=1, ret=<0d1f>
[
[[getKeyDataForOya]] Keycode=93, oya=4, ret=<1e>
$
[[getKeyDataForOya]] Keycode=21, oya=5, ret=<3815ff>
[[{]]
[[getKeyDataForOya]] Keycode=93, oya=5, ret=<381eff>

a{{{{{{

asdfhgzx
objc

```
    // Return thumb key if past simultaneous decision time.
    if (!prefCshift && (gBuff == prefThumbL || gBuff == prefThumbR) &&
        [[NSDate date] timeIntervalSinceDate:gOyaKeyDownTimeStamp] > prefTwait) {
        unsigned char prevBuff = gBuff;
        CGEventFlags prevEventMasks = gEventMasks;
        switch(gBuff) {
            case kVK_Option: 
            case kVK_RightOption:
                  gEventMasks &= ~kCGEventFlagMaskAlternate;    break;
            case kVK_Command:
            case kVK_RightCommand:
                  gEventMasks &= ~kCGEventFlagMaskCommand;      break;
            case kVK_Shift: 
            case kVK_RightShift:        
            	gEventMasks &= ~kCGEventFlagMaskShift;        break;
            case kVK_CapsLock:
                gEventMasks &= ~kCGEventFlagMaskAlphaShift;   break;
            case kVK_Control:
            	gEventMasks &= ~kCGEventFlagMaskControl;      break;
        }
        startTimer(0);
        fireTimer();
        
        // If your thumb is the modifier key, press it again as the modifier key, not the thumb key.
        if (prevEventMasks != gEventMasks) {
            myCGEventPostToPid(targetPid, CGEventCreateKeyboardEvent(source, prevBuff, YES));
            // if you don't yield, the order is reversed.
            [[NSRunLoop currentRunLoop] runUntilDate:[NSDate dateWithTimeIntervalSinceNow:0.05f]];
        }
    }

```


- [Auto Layout Guide: Working with Constraints in Interface Builder](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/AutolayoutPG/WorkingwithConstraintsinInterfaceBuidler.html#//apple_ref/doc/uid/TP40010853-CH10-SW1)

---
This page is auto-translated from [/nishio/Lacaille改造](https://scrapbox.io/nishio/Lacaille改造) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.