# Dependencies

Data Binding
apply plugin: 'kotlin-kapt'

android {
    dataBinding {
        enabled = true
    }
}

kapt 'com.android.databinding:compiler:3.0.1'


# Latest Android version of dependencies

Put this in main build.gradle

    ext {
        global_compileSdkVersion = 26
        global_buildToolsVersion = "26.0.2"

        minimumSdkVersion = 16
        targetedSdkVersion = 26

        supportLibVersion = '26.1.0'
        playServiceVersion = '11.6.0'

        kotlin_version = '1.1.60'
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


Dependenies verisons

    distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip

    classpath 'com.android.tools.build:gradle:3.0.0'
    classpath 'io.fabric.tools:gradle:1.24.5'
    
    implementation "com.android.support:appcompat-v7:$supportLibVersion"
    implementation "com.android.support:cardview-v7:$supportLibVersion"
    implementation "com.android.support:design:$supportLibVersion"
    
    implementation 'com.google.code.gson:gson:2.8.0'
    
    implementation 'com.squareup.picasso:picasso:2.5.2'
    implementation "com.google.android.gms:play-services-gcm:$playServiceVersion"
    implementation 'com.clevertap.android:clevertap-android-sdk:3.1.6'
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jre7:$kotlin_version"
    
    implementation(name: 'release-base-4.4', ext: 'aar')
    implementation(name: 'release-net-1.3', ext: 'aar')
    implementation(name: 'release-datepicker-1.9', ext: 'aar')
    implementation(name: 'release-timepicker-1.4', ext: 'aar')
    
    implementation('com.crashlytics.sdk.android:crashlytics:2.6.8@aar') {
        transitive = true;
    }
    
    
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
