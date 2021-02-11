# Flutter Podfile Error Fixed

Here are some common Pod related problem fixings that I've faced during developing Flutter apps for iOS.

## Module not found on Xcode

It happens when podfile doesn't contain any dependencies, to solve this problem run these commands on your mac terminal / VS Code terminal, make sure you close Xcode.

`cd ios`

`pod cache clean --all`

`rm Podfile`

`flutter clean`

`pod init`

`flutter pub get`

`pod install`


Notice: If your pod doesn't install anything even if you did the above steps, there is something that needs to do with cocoapods, it may show `FLUTTER_ROOT` is unknown, something like this.

Do these steps on your terminal on `/ios` folder

`rm -rf ~/.cocoapods/repos/Spec_Lock`

`rm -rf ~/.cocoapods/repos/trunk/`

