# MCHelpGestureRecognizer
### A simple way to add help functionality into your app without the need for a button

![Example Gif](http://i.imgur.com/N2pFAGv.gif)

To use, simply import `MCHelpGestureRecognizer.h` and `MCHelpGestureRecognizer.m` into your project (like any other `UIGestureRecognizer`).

```objective-c
helpRecognizer = [[MCHelpGestureRecognizer alloc] initWithTarget:self action:@selector(showHelp)];
[helpRecognizer setDelegate:self];
[self.view addGestureRecognizer:helpRecognizer];
```


And then add a callback method:

```objective-c
-(void)showHelp
{
    NSLog(@"HELP ME!");
}
```

Also, implement this delegate method to allow interaction with other UI Objects:

```objective-c
- (BOOL)gestureRecognizer:(UIGestureRecognizer *)gestureRecognizer shouldReceiveTouch:(UITouch *)touch {
    if ([touch.view isKindOfClass:[UIControl class]]) {
        return NO;
    }
    return YES;
}
```


Simples!

Oh, and yes, it's MIT licensed. Go wild!
