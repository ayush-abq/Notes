**Publishing iOS App to App Store - README**

### Prerequisites:
1. **Mac Setup:**
   - Ensure you have a Mac with Xcode installed. [Download Xcode](https://apps.apple.com/us/app/xcode/id497799835) from the Mac App Store.
2. **Apple Developer Account:**
   - Create an Apple Developer account if you don't have one: [Apple Developer Program](https://developer.apple.com/).
3. **iOS Developer Certificate:**
   - Generate an iOS developer certificate in the [Apple Developer Center](https://developer.apple.com/account/resources/certificates/list).
4. **Provisioning Profile:**
   - Create an App ID and provisioning profile in the [Apple Developer Center](https://developer.apple.com/account/resources/identifiers/list).
5. **Node.js and NPM:**
   - Make sure Node.js and npm are installed on your machine.

### Project Setup:
- Clone your project from GitHub.
  ```bash
  npm install && cd ios && pod install && cd ..
  ```
- Resolve any errors. If encountering issues, remove the pod file using `cd ios && pod install`.

### Xcode Configuration:
- Open the project in Xcode.
- Build the project (`Product -> Build`).
- Resolve any errors. For permissions (e.g., camera or gallery), update the Info.plist file.

### Firebase Integration:
- If using Firebase notifications, add the following lines to your Podfile:
  ```ruby
  pod 'Firebase', :modular_headers => true
  pod 'FirebaseCoreInternal', :modular_headers => true
  pod 'GoogleUtilities', :modular_headers => true
  pod 'FirebaseCore', :modular_headers => true
  ```
- Disable the line:
  ```ruby
  # :flipper_configuration => flipper_config,
  ```

### React Native Build:
- Add the following script in the `package.json` file:
  ```json
  "build:ios": "react-native bundle --entry-file='index.js' --bundle-output='./ios/main.jsbundle' --dev=false --platform='iOS'"
  ```

### Firebase Import:
- Import Firebase in `AppDelegate.mm`:
  ```objective-c
  #import <Firebase.h>
  ```

### Simulator Testing:
- Build the app and test on the simulator. Resolve any errors.

### App Store Submission:
- In Xcode, go to signing and capabilities. Select your team and provisioning profile.
- Build the app (`Product -> Archive`). Ensure you're building for "Any iOS device (arm64)."
- Choose `Distribute -> TestFlight and App Store`.
- The build will be sent to App Store Connect. Submit your app on the [App Store Connect](https://appstoreconnect.apple.com/).

**Note:** Always double-check each step and resolve any issues before proceeding to the next.

### References Video links:
 - https://www.youtube.com/watch?v=4Q4tip0cDsM
 - https://www.youtube.com/watch?v=YE0bp7_npKE
