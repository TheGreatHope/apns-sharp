# Introduction #

This Library is designed to use a PKCS12 format Certificate file, which includes the Private Key and Certificate in a single container.  This page will show you how to generate this file using the Certificates you downloaded from _iPhone Developer Program Portal_ in either OSX's Keychain or using OpenSSL.


# Details #

## OSX Keychain ##
After you've created the appropriate Push Notification Certificate in _iPhone Developer Program Portal_ you should have downloaded a file named something like _apn\_developer\_identity.cer_.  If you have not done so already, you should open/import this file into Keychain, into your _login_ section.

Finally, if you filter Keychain to show your _login_ container's Certificates, you should see your Certificate listed.  Expand the certificate, and there should be a Key underneath/attached to it.

Right Click or Ctrl+Click on the appropriate Certificate and choose _Export_.  Keychain will ask you to choose a password to export to.  Pick one and remember it.  You should end up with a _.p12_ file.  You will need this file and the password you picked to use the Notification and Feedback Libraries here.


## OpenSSL ##
Here is how to create a PKCS12 format file using open ssl, you will need your developer private key (which can be exported from the keychain) and the CertificateSigningRequest??.certSigningRequest

  * 1. Convert apn\_developer\_identity.cer (der format) to pem:
> `openssl x509 -in apn_developer_identity.cer -inform DER -out apn_developer_identity.pem -outform PEM`}

  * 2. Next, Convert p12 private key to pem (requires the input of a minimum 4 char password):
> `openssl pkcs12 -nocerts -out private_dev_key.pem -in private_dev_key.p12`

  * 3. (Optional): If you want to remove password from the private key:
> `openssl rsa -out private_key_noenc.pem -in private_key.pem`

  * 4. Take the certificate and the key (with or without password) and create a PKCS#12 format file:
> `openssl pkcs12 -export -in apn_developer_identity.pem -inkey private_key_noenc.pem -certfile CertificateSigningRequest??.certSigningRequest -name "apn_developer_identity" -out apn_developer_identity.p12`