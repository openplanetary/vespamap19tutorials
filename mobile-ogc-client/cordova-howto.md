# [Apache Cordova](https://cordova.apache.org/)

## Android / Linux

### Install location
  ```
  export BASEDIR=~/android
  mkdir $BASEDIR
  ```

### Prerequisites 

- [Android SDK Tools](https://developer.android.com/studio/index.html)
  ```
  cd $BASEDIR; unzip ~/Downloads/sdk-tools-linux-4333796.zip
  export PATH=$BASEDIR/tools:$PATH
  ```

- [Gradle (build system)](https://gradle.org/install/)
  ```
  cd $BASEDIR; unzip ~/Downloads/gradle-5.5-bin.zip
  export PATH=$BASEDIR/gradle-5.5/bin:$PATH
  ```

- [Direct dependencies for Cordova](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html)
  ```
  sdkmanager "build-tools;29.0.0"
  sdkmanager "extras;android;m2repository"
  sdkmanager platform-tools
  ```
- [Setup Environment Variables](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#setting-environment-variables)
  ```
  export ANDROID_HOME=$BASEDIR
  export PATH=$BASEDIR/platform-tools:$PATH
  ```  

### Android Emulator

- [Set up android emulator](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#setting-up-an-emulator)
  ```
  sdkmanager "system-images;android-29;google_apis;x86_64"
  sdkmanager emulator
  avdmanager list
  avdmanager create avd -d 17 -n pixel -k "system-images;android-29;google_apis;x86_64"
  emulator -list-avds
  emulator @pixel
  ```

### Cordova

- [Install cordova and create HelloWorld](https://cordova.apache.org/docs/en/latest/guide/cli/index.html#create-the-app)
  ```
  npm install -g cordova
  cordova create OPmap org.openplanetary.opmap OPmap
  ls OPmap
  ```
- [Add platform](https://cordova.apache.org/docs/en/latest/guide/cli/index.html#add-platforms)
  ```
  cd OPmap
  cordova platform add android
  ```
- Adapt HelloWorld template
  ```
  vi www/index.html
  ```
  (paste leaflet code from @chbrandt, [./app/index.html](./app/index.html) )
- Compile APK package
  ```
  cordova build
  ```
- Run Cordova in the emulator
  ```
  cordova run android
  ```
- Run Cordova in your device
  ```
  CTRL-C
  sudo $BASEDIR/platform-tools/adb devices
  cordova run android
  ```
  
