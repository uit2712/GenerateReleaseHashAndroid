# GenerateReleaseHashAndroid

--------------------Generate Release Key Hash Android--------------------

<h2>STEP 1:</h2>
+ Download openssl from https://code.google.com/archive/p/openssl-for-windows/downloads<br/>
+ Download Java Development Kit (JDK) 8
<h2>STEP 2:</h2> Extract and copy folder to Disk 'C:\', rename it to 'openssl'
<h2>STEP 3:</h2> Edit 'path' in 'System variables'
Add new path to your openssl's bin folder: 'C:\openssl\bin'
<h2>STEP 4:</h2> Add new 'User variable' OPENSSL_CONF references to your 'openssl.cnf' file:
OPENSSL_CONF: 'C:\openssl\openssl.cnf'
<h2>STEP 5:</h2> Go to your jdk's bin folder (often: C:\Program Files (x86)\Java\jdk1.8.0_141\bin).<br/>
Then, open command line from here
<h2>STEP 6:</h2> Type this command and copy your key hash:
<pre>
keytool -exportcert -alias androiddebugkey -keystore my_key.keystore | OPENSSL sha1 -binary | OPENSSL base64
</pre>
