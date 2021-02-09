# REACT NATIVE APPLICATION DEPLOYMENT PROCESS

## WITH EXPO




```
expo publish
```

```
expo build
```

- Once build is completed, Run the following command and save the keys in secure place since they will be required in future
```
expo fetch:android:keystore
```

- Download bundletool latest release from github repo for extraction of .apks from .aab

- After build is done. A .aab file will be produced. 

- Download the .aab in same bundletool.jar folder and run the following command. Here the .jar file name might be different for you.
	- "--bunle=" is the path where .aab file is downloaded and "--output=" is the path where you want the .apks to reside.
	- "--ks=" is the path where .jks file is stored after running the previous command and "--ks-key-alias=" is the attribute value in that .jks file

### FOR TESTING ON YOUR DEVICE ONLY

```
java -jar bundletool-all-1.4.0.jar build-apks --bundle=/MyApp/my_app.aab --output=/MyApp/my_app.apks --ks=/MyApp/keystore.jks --ks-key-alias=MyKeyAlias 
```

- Now you will get .apks file containing various apks aka android bundle.

- To try and run the app on your connected device run 
	- "--apks=" is the path where the .apks file is present

```
java -jar bundletool-all-1.4.0.jar install-apks --apks=/MyApp/my_app.apks

```

- After successfully running all the commands above you must have a fully running app on the connected device

### FOR SHARING THE APP TO COLLEAGUES 

```
java -jar bundletool-all-1.4.0.jar build-apks --bundle=/MyApp/my_app.aab --output=/MyApp/my_app.apks --ks=/MyApp/keystore.jks --ks-key-alias=MyKeyAlias --mode=universal

```

- Change the .apks file extension to .zip

- Extract the file content and share universal.apk

## WITHOUT EXPO 

-- COMING SOON...