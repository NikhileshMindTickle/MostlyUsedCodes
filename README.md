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


Dependenies verisons

    distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip

    classpath 'com.android.tools.build:gradle:3.0.0'
    classpath 'io.fabric.tools:gradle:1.24.5'
    
    compile "com.android.support:appcompat-v7:$supportLibVersion"
    compile "com.android.support:cardview-v7:$supportLibVersion"
    
    compile 'com.google.code.gson:gson:2.8.0'
    
    compile 'com.squareup.picasso:picasso:2.5.2'
    compile "com.google.android.gms:play-services-gcm:$playServiceVersion"
    compile 'com.clevertap.android:clevertap-android-sdk:3.1.6'
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jre7:$kotlin_version"
    
    implementation(name: 'release-base-4.4', ext: 'aar')
    implementation(name: 'release-net-1.3', ext: 'aar')
    implementation(name: 'release-datepicker-1.9', ext: 'aar')
    implementation(name: 'release-timepicker-1.4', ext: 'aar')
    
    compile('com.crashlytics.sdk.android:crashlytics:2.6.8@aar') {
        transitive = true;
    }
