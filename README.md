# Yubikey Best Practices

We suggest buying at least two [Yubikeys](https://www.yubico.com/products/yubikey-5-overview/), e.g. Yubikey NFC and Nano. This way you have one key for your key chain and mobile and one small e.g. for laptops etc.

## KeepassXC and Yubikey

You can use a Yubikey for a second secret using Challenge-Response.

### Configure Yubikey for Challenge-Response

First you need to configure your Yubikeys for Challenge-Response.

> **WARNING:** Use at least two keys and print out and secure your secret!

* Install the [Yubikey Manager](https://www.yubico.com/support/download/yubikey-manager/) and start it. Some OS provide already packages, e.g. Archlinux `yubikey-manager`.
* Select "Applications" -> "OTP".

![Challenge-Response Configuration](img/cr1.png)

* Select "Configure" for "Long Touch (Slot 2)".

![Challenge-Response Configuration](img/cr2.png)

* Select "Challenge-response" and click "Next".

![Challenge-Response Configuration](img/cr3.png)

* On the first key you set up you can use "Generate" to create a secret. On every following key you will have to copy this key to this field. Select "Require touch" and end configuration with "Finish".

  >  **WARNING: Secure this key, so that you can copy it to another key. Once you click "Finish" you won't be able to get the secret again.

![Challenge-Response Configuration](img/cr4.png)

* Now you should set up another key and secure your secret. We suggest printing it an keep is somewhere safe.
* Remove Yubikey and insert the new Yubikey. Start Yubikey Manager.
* Configure "Slot 2" for Challenge-response.
* This time **DO NOT** generate a secret. Copy your saved secret from key one to this field.

Once your Yubikeys are configured, go to the next step, Configuring KeepassXC for Yubikey.

### Configuring KeepassXC for Yubikey

> **WARNING:** First make sure you have at least two Yubikeys configures for Challenge-Response and cave a copy and backup of the secret. If you lose this credentials you won't be able to open your database!
>
> When you modify an existing database it is recommended to create a backup first.

Start your existing KeepassXC database. If you are creating a new database the window for password will look the same, you will need to "Add additional protection", as well.

* Start KeepassXC, open existing database and select "Database" -> "Database Settings".

![Challenge-Response Configuration](img/keepass1.png)

* Select "Security" on the left and select "Add additional protection".

![Challenge-Response Configuration](img/keepass2.png)

* Select "Add Challenge-Response".

![Challenge-Response Configuration](img/keepass3.png)

* Select the slot on your Yubikey. If it is not inserted yet, insert a Yubikey and click "Refresh" Finish configuration with with "OK".

![Challenge-Response Configuration](img/keepass4.png)

Tap your Yubikey. Your configuration is saved.

![Challenge-Response Configuration](img/keepass5.png)

* To open your database you need to insert your Yubikey. And then type in your password. Once you try to unlock your database KeepassXC will ask you to tap your Yubikey for Challenge-Response. If your key is not listed, click "Refresh" and select the correct slot.

![Challenge-Response Configuration](img/keepass6.png)

> **WARNING:** Test every newly configured Yubikey for a working Challenge-Response configuration!
