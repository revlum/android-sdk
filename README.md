# Implementation

Before we can get started with implementing the SDK, you should retrieve your API Key for your integration from the Revlum Dashboard.

## 1. Add gradle dependency
Either use jitpack by, for example (more info at https://jitpack.io/):

```
   repositories {
        mavenCentral()
        maven { url "https://jitpack.io" }
   }
   dependencies {
	implementation 'com.github.revlum:android-sdk:v1.0.0'
   }

```

Or manually add the .aar file:
  Download the .aar file from the releases in this repo.

  Add library dependency to your app's module level build.gradle file -> Instructions can be found here:
  https://developer.android.com/studio/projects/android-library#psd-add-aar-jar-dependency
  

## 2. Register the activity

  Add the OfferwallActivity to your app's AndroidManifest.xml file.
```
<application

...

<activity
	android:name="com.revlum.offerwallsdk.OfferwallActivity">
</activity>

</application>
```
  

## 3. Initialize the SDK

At any point before launching the offerwall activity, setup the offerwall configuration by calling the `Offerwall.configure` method and providing it an API key and a user ID.
```
import com.revlum.offerwallsdk.Offerwall

...

Offerwall.configure(apiKey = "myapikey1234567890", userId = "myuserid")
```
  

## 4. Show the offerwall

Launch the offerwall activity by calling the `Offerwall.launch` method, providing it the context.
```
import com.revlum.offerwall.Offerwall

...

Offerwall.launch(context = context)
```
  

If you're using Jetpack Compose, you can get the context through the LocalContext class.

```
import androidx.compose.ui.platform.LocalContext

...

val context = LocalContext.current
```

if not, pass it your current activity or fragment.
    
