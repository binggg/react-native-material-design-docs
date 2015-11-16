React Native Material Design
=======

## Install [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons)

### Android (experimental)

*Note: Android support requires React Native 0.12 or later*

* Copy the whole `Fonts` folder to `android/app/src/main/assets`. 
* Edit `android/settings.gradle` to look like this:

  ```
  rootProject.name = 'MyApp'

  include ':app'

  //Add the following two lines:
  include ':react-native-vector-icons'
  project(':react-native-vector-icons').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-vector-icons/android')
  ```

* Edit `android/app/build.gradle` (note: **app** folder) to look like this: 

  ```
  apply plugin: 'com.android.application'

  android {
    ...
  }

  dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    compile 'com.android.support:appcompat-v7:23.0.0'
    compile 'com.facebook.react:react-native:0.12.+'

    // Add this line:
    compile project(':react-native-vector-icons')
  }
  ```

* Edit your `MainActivity.java` (deep in `android/app/src/main/java/...`) to look like this:

  ```
  package com.myapp;

  // Add this line:
  import com.oblador.vectoricons.VectorIconsPackage;

  import android.app.Activity;
  ....

  public class MainActivity extends Activity implements DefaultHardwareBackBtnHandler {

    private ReactInstanceManager mReactInstanceManager;
    private ReactRootView mReactRootView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      mReactRootView = new ReactRootView(this);

      mReactInstanceManager = ReactInstanceManager.builder()
        .setApplication(getApplication())
        .setBundleAssetName("index.android.bundle")
        .setJSMainModuleName("index.android")
        .addPackage(new MainReactPackage())

        // and this line:
        .addPackage(new VectorIconsPackage())

        .setUseDeveloperSupport(BuildConfig.DEBUG)
        .setInitialLifecycleState(LifecycleState.RESUMED)
        .build();

      mReactRootView.startReactApplication(mReactInstanceManager, "MyApp", null);

      setContentView(mReactRootView);
    }
    ...
  }
  ```

### Known issues on android

* Size can only be passed as a property, not with a stylesheet
* Icons have a fixed width causing some icons to be clipped or have whitespace. Adjust with `style={{width: xx}}` for now. 
* Icons cannot be nested within a `Text` component.
