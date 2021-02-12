# Flutter Podfile Error Fixed

Here are some common Pod related problem fixings that I've faced during developing Flutter apps for iOS.


## Module not found on Xcode Macbook

The most common problem in flutter with firebase is in it's setup on ios!

On Firebase console, don't follow step 3 (Add Firebase SDK) and step 4 (Add initialization code), as it's described on Flutter documentation.

But unfortunately it shows error after doing so, it shows 


`
ios/Runner/GeneratedPluginRegistrant.m:10:9: fatal
    error: module 'firebase_admob' not found
    @import firebase_admob;
     ~~~~~~~^~~~~~~~~~~~~~
    1 error generated.
`

There is a lot of solution on stackover flow, manually writing pod file, and install them it seems also working.
But let the flutter do this...



1. Manually Delete `ios/.symlinks`
2. Manually Delete `ios/Pods`
3. Manually Delete `ios/Podfile`
4. Manually Delete `ios/Podfile.lock`
5. Then in terminal `flutter clean && flutter run`

It will take some time to install the pod... Have a cup of coffee now.. Woohoo



## Module not found on Xcode (Alternative solution)

It happens when podfile doesn't contain any dependencies, to solve this problem run these commands on your mac terminal / VS Code terminal, make sure you close Xcode.

`cd ios`

`pod cache clean --all`

`rm Podfile`

`flutter clean`

`pod init`

`flutter pub get`

`pod install`


## `FLUTTER_ROOT` is unknown

Do these steps on your terminal on `/ios` folder

`rm -rf ~/.cocoapods/repos/Spec_Lock`

`rm -rf ~/.cocoapods/repos/trunk/`

Then

`flutter clean && flutter run`

Fixed!!!



