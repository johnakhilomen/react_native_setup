# React Native Developer Setup
A hopefully helpful guide to getting a basic setup for React Native development.

_Note: This is a work in progress, I'll keep adding/updating_

## General Setup

* **General JavaScript Setup**
  * If you haven't already done so, follow this [JavaScript Developer Setup](https://gist.github.com/Geoff-Ford/cdf4a3cb291029ed2dfc991b41a057ba) guide

* **Java**
  * `brew install --cask adoptopenjdk/openjdk/adoptopenjdk8`

* **Watchman**
  * `brew install watchman`

* **Xcode**
  * Install Xcode from the [App Store](https://itunes.apple.com/us/app/xcode/id497799835)
  * Once installed, navigate to (Preferences -> Locations) and in the "Command Line Tools" dropdown, select the most recent version
  * To install additional simulators:
    * Navigate to (Preferences -> Components)
    * Click on the download icon next the required OS version i.e. iOS 14.3 Simulator

* **Android Studio**
  * Download and install [Android Studio](https://developer.android.com/studio). Make sure `Android SDK`, `Android SDK Platform` and `Android Virtual Device` are all selected during the installation
  * To install additional SDKs, navigate to (Preferences -> Appearance & Behavior -> System Settings -> Android SDK) and select the required SDK version i.e. Android 11.0 (R)
  * React Native requires some environment variables to be added to your bash (`~/.bash_profile` or `~/.bashrc`) or equivalent (`~/.zprofile` or `~/.zshrc`) config:

        export ANDROID_HOME=$HOME/Library/Android/sdk
        export PATH=$PATH:$ANDROID_HOME/emulator
        export PATH=$PATH:$ANDROID_HOME/tools
        export PATH=$PATH:$ANDROID_HOME/tools/bin
        export PATH=$PATH:$ANDROID_HOME/platform-tools

  * As we just changed the config you will either need to open a new terminal or `source ~/.bash_profile` (or equivalent config file) to update the current terminal window with the changes
  * To install additional emulators:
    * Navigate to (Tools -> AVD Manager) or look for the "AVD Manager" button on the top right of Android Studio
    * Click "+ Create Virtual Device..."
    * Select a "Category" i.e. "Phone" and a model i.e. "Pixel 4 XL" and click "Next"
    * Select a "System Image" i.e. "Q" and click "Next"
    * Make required config changes if any and click "Finish"

* **React Native CLI**
  * If you already have `react-native-cli` installed globally, remove this (`yarn global remove react-native-cli`) as it isn't necessary anymore and can cause issues
  * To use the React Native CLI, we call it like this: `npx react-native <command>`. The current version of the CLI will be downloaded the first time the CLI is used i.e. `npx react-native init MyNewProject`

* https://reactnative.dev/docs/getting-started
* https://reactnative.dev/docs/environment-setup

## Example App

* Create a new project:
  * `yarn react-native init MyNewProject` to create a new project with the name "MyNewProject"
  * Or if you prefer TypeScript `yarn react-native init MyNewProject --template react-native-template-typescript`

* **Bundler**
  * `gem install bundler`
  * `bundle init` to add a `Gemfile` and `Gemfile.lock` to your project
  * https://bundler.io/

* **CocoaPods** - dependancy library for iOS apps
  * `gem install cocoapods` _(Note: Only required when you are first setting up your app)_
  * `cd ios`
  * `bundle exec pod install` to install the required dependencies for your iOS app
  * `cd ..` to go back to root folder
  * https://guides.cocoapods.org/using/getting-started.html

* **Metro Bundler**
  * React Native uses Metro Bundler to bundle up all your project's JavaScript into a file that is then used by your app in both iOS and Android
  * `yarn react-native start`

* **iOS**
  * From another terminal, `yarn react-native run-ios` to build the iOS app and open it in a simulator.
  * Or if you prefer to run from Xcode, open the app at the `ios` folder then look for the `Run` button

* **Android**
  * From another terminal, `yarn react-native run-android` to build the Android app and open it in an emulator.
  * Or if you prefer to run from Android Studio, open the app at the `android` folder then look for the `Run 'app'` button

* [Troubleshoot](https://reactnative.dev/docs/troubleshooting)

## Distribution

* **Fastlane**
  * Add `gem “fastlane”` to your `Gemfile`
  * Then `bundle install` or `bundle update` to add those dependencies
  * In the `ios` or `android` directory of your project `fastlane init`
  * https://docs.fastlane.tools/
  * https://docs.fastlane.tools/getting-started/ios/setup/
  * https://docs.fastlane.tools/getting-started/android/setup/
  * https://docs.fastlane.tools/codesigning/getting-started/

* **Google Play Store**
  * https://reactnative.dev/docs/signed-apk-android
  * https://play.google.com/console/
  * Testing releases: https://support.google.com/googleplay/android-developer/answer/9845334?visit_id=637537832775008783-3879841131&rd=1#zippy=%2Cversion-code-requirements

* **Apple App Store**
  * https://reactnative.dev/docs/publishing-to-app-store
  * https://developer.apple.com/
  * https://appstoreconnect.apple.com/

* **App Center**
  * https://appcenter.ms/
