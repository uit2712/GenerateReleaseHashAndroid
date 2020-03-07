# GenerateReleaseHashAndroid

--------------------Generate Release Key Hash Android--------------------

<h2>STEP 1:</h2>
+ Download openssl from https://code.google.com/archive/p/openssl-for-windows/downloads<br/>
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/1.png' width='700'/>
+ Download and install Java Development Kit (JDK) 8
<h2>STEP 2:</h2> Extract and copy folder to Disk 'C:\', rename it to 'openssl'
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/2.png' width='700'/>
<h2>STEP 3:</h2> Edit 'path' in 'System variables'
Add new path to your openssl's bin folder: 'C:\openssl\bin'
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/3.png' width='700'/>
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/4.png' width='700'/>
<h2>STEP 4:</h2> Add new 'User variable' OPENSSL_CONF references to your 'openssl.cnf' file:
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/5.png' width='700'/>
<h2>STEP 5:</h2> Go to your jdk's bin folder (often: C:\Program Files (x86)\Java\jdk1.8.0_141\bin).<br/>
Then, open command line from here
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/6.1.png' width='700'/>
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/6.2.png' width='700'/>
<h2>STEP 6:</h2> Generating an upload key (if you don't have one)
<pre>
keytool -genkeypair -v -keystore my-upload-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000
</pre>
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/7.png' width='700'/>
<h2>STEP 7:</h2> Type this command and copy your key hash:
<pre>
keytool -exportcert -alias androiddebugkey -keystore my-upload-key.keystore | OPENSSL sha1 -binary | OPENSSL base64
</pre>
<img src='https://github.com/uit2712/GenerateReleaseHashAndroid/blob/master/Images/8.png' width='700'/>
