# LoginWithFacebook
This Demo app will show how to login with facebook and fetch the data like image ,birthday,email and total friends.

## For more details
[https://developers.facebook.com/docs/facebook-login/android](https://developers.facebook.com/docs/facebook-login/android)


Add Dependency at App level Gradle file:

1. Glide is Used to set the Images
       [https://github.com/bumptech/glide](https://github.com/bumptech/glide)
       
       
2. ButterKnife is to instantiate the widget
  [http://jakewharton.github.io/butterknife/](http://jakewharton.github.io/butterknife/)
     
#### 3. Facebook sdk
![dependency](https://user-images.githubusercontent.com/25931598/42662871-dc2601fe-8650-11e8-8528-3b49c3b7c5e3.PNG)



you will get app_id and fb_login_protocol_scheme by creating the project on Developer.facebook.com

Add Metadata and permissions in Manifest File:

## Permission: 
   ### Add Internet Permission

## Metadata and Activity:

    <meta-data android:name="com.facebook.sdk.ApplicationId"
        android:value="@string/facebook_app_id"/>

    <activity android:name="com.facebook.FacebookActivity"
        android:configChanges=
            "keyboard|keyboardHidden|screenLayout|screenSize|orientation"
        android:label="@string/app_name" />

    <activity
        android:name="com.facebook.CustomTabActivity"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.VIEW" />
            <category android:name="android.intent.category.DEFAULT" />
            <category android:name="android.intent.category.BROWSABLE" />
            <data android:scheme="@string/fb_login_protocol_scheme" />
        </intent-filter>
    </activity>

## For Getting the KeyHash Value:
Last and most important past You have to generate keyhash value:
1. You need to install openssl in your computer
2. Goto C:\Program Files\Java\jre1.8.0_161\bin using command prompt
3. Goto openssl >>then bin >> copy that path 
path openssl:  E:\Software\openssl\bin\openssl.exe 
4. enter this command>> 
keytool -exportcert -alias androiddebugkey -keystore "C:\Users\"Username_Of_Your_Computer_Or_Laptop"\.android\debug.keystore" | "Paste_OpenSSl_Path" sha1 -binary |"Paste_OpenSSl_Path " base64


![facebook_login_harsh_key](https://user-images.githubusercontent.com/25931598/42662188-4be7ef3c-864e-11e8-86b3-b7883edc3967.PNG)

5.after this command prompt asked 
Enter KeyStore Password:

![keyhash](https://user-images.githubusercontent.com/25931598/42663074-a935b252-8651-11e8-8018-70e96f44bce3.PNG)
