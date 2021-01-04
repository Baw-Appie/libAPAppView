# libAPAppView
### Get Application View on SpringBoard.

## How to use
To use libAPAppView, copy `libAPAppView.h` to `$THEOS/include` and `libAPAppView.dylib` to `$THEOS/lib`. Then you can add `XXX_LIBRARIES = APAppView` to your Makefile and `#import <libAPAppView.h>` into any source files you want to use it in. Then add `Depends: com.rpgfarm.libapappview` to your control file.

## APAppView Interface
```objc
@interface APAppView
-(UIView *)viewForBundleID:(NSString *)bundleID;
-(void)stopAppView;
@end
```

## [Example] Get stock "Calculator" application view
```objc
APAppView *appView = [[APAppView alloc] init];
[yourView addSubview:[appView viewForBundleID:@"com.apple.calculator"]];

--- when viewwilldisappear ---

[appView stopAppView];
```
