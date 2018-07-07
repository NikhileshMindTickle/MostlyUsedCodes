# Dependencies

*Data Binding*
```
apply plugin: 'kotlin-kapt'

android {
    dataBinding {
        enabled = true
    }
}

kapt 'com.android.databinding:compiler:3.0.1'
```
*Kotlin Enable*
```
apply plugin: 'kotlin-android'

apply plugin: 'kotlin-android-extensions'

//Kotlin
implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
```

# Latest Android version of dependencies

Put this in main build.gradle
```
ext {
    globalCompileSdkVersion = 27
    globalBuildToolsVersion = "27.0.3"

    minimumSdkVersion = 16
    targetedSdkVersion = 27

    supportLibVersion = '27.1.1'
    playServiceVersion = '15.0.1'

    kotlinVersion = '1.2.51'

    retrofitVersion="2.4.0"
}

repositories {
    google()
    jcenter()
}

allprojects {
    repositories {
        google()
        jcenter()
        mavenCentral()
        maven { url "https://jitpack.io" }
        flatDir {
            dirs 'libs'
        }
    }
}
```

Dependenies verisons
```
distributionUrl=https\://services.gradle.org/distributions/gradle-4.8-all.zip

classpath 'com.android.tools.build:gradle:3.2.0-alpha18'
classpath 'io.fabric.tools:gradle:1.24.5'

//Kotlin
implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"

//Support
implementation "com.android.support:support-v4:$supportLibVersion"
implementation "com.android.support:appcompat-v7:$supportLibVersion"
implementation "com.android.support:cardview-v7:$supportLibVersion"
implementation "com.android.support:design:$supportLibVersion"

//Constraint Layout
implementation 'com.android.support.constraint:constraint-layout:1.1.2'

//Gson
implementation 'com.google.code.gson:gson:2.8.0'

//Picasso
implementation 'com.squareup.picasso:picasso:2.5.2'

//Play Services
implementation "com.google.android.gms:play-services-gcm:$playServiceVersion"
implementation "com.google.android.gms:play-services-location:$playServiceVersion"

//Clever Tap
implementation 'com.clevertap.android:clevertap-android-sdk:3.1.6'

//Niks Libraries
//noinspection GradlePath
implementation files('releases/release-base-4.6.aar')
//noinspection GradlePath
implementation files('releases/release-net-1.4.aar')
//noinspection GradlePath
implementation files('releases/release-timepicker-1.4.aar')
//noinspection GradlePath
implementation files('releases/release-datepicker-1.9.aar')
//noinspection GradlePath
implementation files('releases/release-locationhelper-1.2.aar')

//Retrofit
implementation "com.squareup.retrofit2:retrofit:$retrofitVersion"
implementation "com.squareup.retrofit2:converter-gson:$retrofitVersion"
implementation "com.squareup.retrofit2:adapter-rxjava2:$retrofitVersion"

//Rx Java
implementation 'io.reactivex.rxjava2:rxandroid:2.0.2'
implementation 'io.reactivex.rxjava2:rxjava:2.1.16'

//Rx view binding helper
implementation 'com.jakewharton.rxbinding2:rxbinding:2.1.1'

//Testing
testImplementation 'junit:junit:4.12'
androidTestImplementation 'com.android.support.test:runner:1.0.2'
androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.2'

implementation('com.crashlytics.sdk.android:crashlytics:2.6.8@aar') {
    transitive = true;
}
```
    
Android User Agent
```
    Mozilla/5.0 (Linux; Android 6.0; Redmi Pro Build/MRA58K)
```

iOS User Agent
```
    Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

GCM Get Token   
```
private class GCMRegister extends AsyncTask<String, String, String> {
        @Override
        protected String doInBackground(String... params) {
            try {
                if (gcm == null) {
                    gcm = GoogleCloudMessaging.getInstance(getApplicationContext());
                }
                String gcmId = gcm.register(getResources().getString(R.string.gcm_sender_id));
                storeSharedPreferenceString("gcm_id",gcmId);
                CustomLogger.Log(TAG,"GCM : "+gcmId);
            } catch (Exception e) {
            }
            return "";
        }
}
```
