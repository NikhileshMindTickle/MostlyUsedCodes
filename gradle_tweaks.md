# gradle.properties 
(Add this in path user/.gradle/gradle.properties)
```
org.gradle.daemon=true
org.gradle.jvmargs=-Xmx8096m -XX:MaxPermSize=2024m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8
org.gradle.parallel=true
org.gradle.configureondemand=false
android.useAndroidX=true
android.enableJetifier=true
org.gradle.caching=true
android.enableBuildCache=true
kapt.incremental.apt=true
kapt.use.worker.api=true
kapt.include.compile.classpath=false
```

# Compiler
Add this in compiler in android studio preferences(remove --daemon as it is overrided)
```
-P disable-performance-plugin -P devBuild -P disableLeakCanary --offline --profile --configure-on-demand --build-cache --parallel --daemon
```

# Gradle Commands
```
./gradlew --status
./gradlew --stop
pkill -f '.*GradleDaemon.*'
```
