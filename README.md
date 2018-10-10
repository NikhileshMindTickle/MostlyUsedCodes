# Zoom Emulator
Cmd + Down Arrow = Decrease Screen Size
Cmd + Up Arrow = Increase Screen Size
Cmd + Right Arrow = Change Screen Orientation

# Dependencies

*Data Binding*
```
apply plugin: 'kotlin-kapt'

android {
    dataBinding {
        enabled = true
    }
}
//Data Binding
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

	//Kotlin
	kotlinVersion = '1.2.51'

	//Support
	supportLibVersion = '27.1.1'

	//Play Services
	playServiceVersion = '15.0.1'

	//Paging Library
	pagingVersion = "1.0.1"
	rxPaggingVersion = '1.0.1'

	//Constraint Layout
	constraintLayoutVersion = "1.1.2"

	//Multidex
	multidexVersion = '1.0.3'

	//Android Navigation
	archNavigationVersion = "1.0.0-alpha02"

	//Glide
	glideVersion="4.6.1"

	//Firebase
	firebaseCoreVersion="16.0.1"
	firebaseVersion = '17.1.0'
	firebaseAuthVersion = '16.0.2'
	firebaseJobDispatcher="0.8.5"

	//Retrofit & OkHttp
	retrofitVersion="2.4.0"

	//Ok Http
	okhttpVersion = '3.10.0'

	//Stetho
	stethoVersion = '1.5.0'

	//Rx Java
	rxjavaVersion="2.1.9"

	//Rx Java Android
	rxandroidVersion = '2.0.2'

	//Rx Java 2 Debug
	rxJavaDebug= "1.2.2"

	//Rx Kotlin
	rxkotlinVersion = '2.2.0'

	//Rx Relay
	rxrelay_version = '2.0.0'

	//Rx Binding
	rxBindingVersion = '2.1.1'

	//Room
	archRoomVersion = '1.1.1'

	//Dagger
	daggerVersion = '2.16'

	//Anko
	ankoVersion = '0.10.4'

	//Leak Canary
	leakcanaryVersion = '1.5'

	//Lifecycle and LiveData and ViewModel
	lifecycleVersion = '1.1.0'
	lifecycleExtVersion = '1.1.1'

	//Timber
	timberVersion = '4.7.0'

	//Testing
	jsonVersion = '20140107'
	junitVersion = '4.12'
	archCoreTesting = '1.1.1'
	testRunnerVersion = '1.0.2'
	espressoVersion = '3.0.2'

	//Robolectric
	robolectricVersion = '3.8'
	robolectricMultidexVersion = '3.3'

	//Mockito
	mokitoVersion = '2.8.9'
	mokitoAndroidVersion = '2.7.22'

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
distributionUrl=https\://services.gradle.org/distributions/gradle-4.9-rc-1-all.zip

//Main
classpath 'com.android.tools.build:gradle:3.3.0-alpha03'
classpath 'io.fabric.tools:gradle:1.24.5'

//Kotlin
implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlinVersion"

//Support
implementation "com.android.support:support-v4:$supportLibVersion"
implementation "com.android.support:appcompat-v7:$supportLibVersion"
implementation "com.android.support:cardview-v7:$supportLibVersion"
implementation "com.android.support:gridlayout-v7:$supportLibVersion"
implementation "com.android.support:support-v13:$supportLibVersion"
implementation "com.android.support:design:$supportLibVersion"
implementation "com.android.support:recyclerview-v7:$supportLibVersion"
implementation "com.android.support:transition:$supportLibVersion"

//Play Services
implementation "com.google.android.gms:play-services-gcm:$playServiceVersion"
implementation "com.google.android.gms:play-services-location:$playServiceVersion"

//Paging Library
implementation "android.arch.paging:runtime:$pagingVersion"
implementation "android.arch.paging:runtime:$pagingVersion"
implementation "android.arch.paging:rxjava2:$rxPaggingVersion"
testImplementation "android.arch.paging:common:$pagingVersion"

//Constraint Layout
implementation "com.android.support.constraint:constraint-layout:$constraintLayoutVersion"

//Multidex
implementation "com.android.support:multidex:$multidexVersion"

//Android Navigation
implementation "android.arch.navigation:navigation-fragment-ktx:$archNavigationVersion"
implementation "android.arch.navigation:navigation-ui-ktx:$archNavigationVersion"

//Picasso
//implementation 'com.squareup.picasso:picasso:2.5.2'

//Clever Tap
implementation 'com.clevertap.android:clevertap-android-sdk:3.1.6'

//Glide
implementation "com.github.bumptech.glide:glide:$glideVersion"
kapt "com.github.bumptech.glide:compiler:$glideVersion"
implementation 'jp.wasabeef:glide-transformations:3.1.1'

//Firebase
implementation "com.google.firebase:firebase-core:$firebaseCoreVersion"
implementation "com.google.firebase:firebase-messaging:$firebaseVersion"
implementation "com.google.firebase:firebase-auth:$firebaseAuthVersion"
implementation 'com.firebase:firebase-jobdispatcher:$firebaseJobDispatcher'

//Gson
implementation 'com.google.code.gson:gson:2.8.0'

//Retrofit & OkHttp
implementation "com.squareup.retrofit2:retrofit:$retrofitVersion"
implementation "com.squareup.retrofit2:converter-gson:$retrofitVersion"
implementation "com.squareup.retrofit2:adapter-rxjava2:$retrofitVersion"

//Loader
implementation 'com.wang.avi:library:2.1.3'

//Ok Http
implementation "com.squareup.okhttp3:logging-interceptor:$okhttpVersion"
implementation "com.squareup.okhttp3:okhttp:$okhttpVersion"
testImplementation "com.squareup.okhttp3:mockwebserver:$okhttpVersion"

//Stetho
implementation "com.facebook.stetho:stetho:$stethoVersion"
implementation "com.facebook.stetho:stetho-okhttp3:$stethoVersion"

//Rx Java
implementation "io.reactivex.rxjava2:rxjava:$rxjavaVersion"

//Rx Java Android
implementation "io.reactivex.rxjava2:rxandroid:$rxandroidVersion"

//Rx Java 2 Debug
implementation 'com.akaita.java:rxjava2-debug:$rxJavaDebug'

//Rx Kotlin
implementation "io.reactivex.rxjava2:rxkotlin:$rxkotlinVersion"

//Rx Relay
implementation "com.jakewharton.rxrelay2:rxrelay:$rxrelay_version"

//Rx Binding
implementation "com.jakewharton.rxbinding2:rxbinding:$rxBindingVersion"


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

//Room
implementation "android.arch.persistence.room:runtime:$archRoomVersion"
kapt "android.arch.persistence.room:compiler:$archRoomVersion"
implementation "android.arch.persistence.room:rxjava2:$archRoomVersion"
testImplementation "android.arch.core:core-testing:$archRoomVersion"
testImplementation "android.arch.persistence.room:testing:$archRoomVersion"

//Dagger
implementation "com.google.dagger:dagger:$daggerVersion"
kapt "com.google.dagger:dagger-compiler:$daggerVersion"
kapt "com.google.dagger:dagger-android-processor:$daggerVersion"
implementation "com.google.dagger:dagger-android-support:$daggerVersion"

//Anko
implementation "org.jetbrains.anko:anko-sdk25:$ankoVersion"
//sdk15, sdk19, sdk21, sdk23 are also available
implementation "org.jetbrains.anko:anko-appcompat-v7:$ankoVersion"
//Coroutine listeners for Anko Layouts
implementation "org.jetbrains.anko:anko-sdk25-coroutines:$ankoVersion"
implementation "org.jetbrains.anko:anko-appcompat-v7-coroutines:$ankoVersion"
//Commons
implementation "org.jetbrains.anko:anko-commons:$ankoVersion"
//For Snackbar
implementation "org.jetbrains.anko:anko-design:$ankoVersion"

//Leak Canary
debugImplementation "com.squareup.leakcanary:leakcanary-android:$leakcanaryVersion"
releaseImplementation "com.squareup.leakcanary:leakcanary-android-no-op:$leakcanaryVersion"

//About
implementation('com.mikepenz:aboutlibraries:5.8.1@aar') {
    transitive = true
}

//Crashlytics
implementation('com.crashlytics.sdk.android:crashlytics:2.9.1@aar') {
    transitive = true
}


//Lifecycle and LiveData and ViewModel
implementation "android.arch.lifecycle:runtime:$lifecycleVersion"
implementation "android.arch.lifecycle:extensions:$lifecycleExtVersion"
implementation "android.arch.lifecycle:common-java8:$lifecycleExtVersion"
kapt "android.arch.lifecycle:compiler:$lifecycleExtVersion"

//Timber
implementation "com.jakewharton.timber:timber:$timberVersion"


//Testing
testImplementation "org.json:json:$jsonVersion"
testImplementation "junit:junit:$junitVersion"
testImplementation "com.android.support:support-annotations:$supportLibVersion"
androidTestImplementation "android.arch.core:core-testing:$archCoreTesting"
androidTestImplementation "com.android.support.test:runner:$testRunnerVersion"
androidTestImplementation "com.android.support.test:rules:$testRunnerVersion"
androidTestImplementation "com.android.support.test.espresso:espresso-core:$espressoVersion"

//Robolectric
testImplementation "org.robolectric:robolectric:$robolectricVersion"
testImplementation "org.robolectric:shadows-multidex:$robolectricMultidexVersion"

//Mockito
testImplementation "org.mockito:mockito-core:$mokitoVersion"
testImplementation "org.mockito:mockito-inline:$mokitoVersion"
androidTestImplementation "org.mockito:mockito-android:$mokitoAndroidVersion"

//ExoPlayer
implementation 'com.google.android.exoplayer:exoplayer:2.7.1'
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
