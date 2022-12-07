# Documentation
## In-App purchasing running on iOS and Android through React Native

# Index

- Starting Project to Android (Emulator)
- Compiling the project for Google Play
- Start the project for iOS (Simulator)
- Compiling the project for iOS (TestFlight)



### Starting Project
The app was developed in [React Native](https://reactnative.dev/) and you need to follow a few steps to compile a project to RN 
This [documentation](https://reactnative.dev/docs/environment-setup) can help you set up the environment for your operating system 
> Note: The environment was set up using the **React Native CLI**


### Starting Project to Android (Emulator)
```sh
yarn install
yarn android
```
### Compiling the project for Google Play
The react native [documentation](https://reactnative.dev/docs/signed-apk-android) suggests that you create a key to sign the project, but at this point you don't need to worry about that. the key is inside the project
```sh
cd android
./gradlew bundleRelease
```
After running these commands, an app-release.aab file will be created in the **android/app/build/outputs/bundle/release/** folder
You need to upload this file to the **Internal Testing** tab in google play
To make this publication, create a new Release and upload the .aab file and **send to review** (Don't worry, the app will not be open to the public)

## Start the project for iOS (Simulator)
```sh
cd ios
pod install 
#maybe you need to set ruby and gems (cocoapods) on your Mac OS
yarn install
yarn ios
```
In the iOS simulator Apple uses the sandbox environment with StoreKit, that is, in the Simulator the App does not go to the cloud to send some information. Everything happens on the machine itself and even the signatures are fake (I know that the initial idea was to test everything on the apple cloud, but this is the expected behavior said by the documentation)

## Compiling the project for iOS (TestFlight)
```sh
cd ios
pod install 
```

Open your Xcode, select the Any iOS Device (arm64) option
![xcode image](https://raw.githubusercontent.com/thiagoabreuch2/recurly-android-and-ios/main/xcode.png?token=GHSAT0AAAAAAB3MAVZNTLQ7XSUMINH2SFCYY4Q5JEA "xcode image")

Then click Product / Build on the top menu
![xcode image](https://raw.githubusercontent.com/thiagoabreuch2/recurly-android-and-ios/main/buildiOS.png?token=GHSAT0AAAAAAB3MAVZM2RJK72MPAM7HXPKSY4Q5JWA "xcode image")




