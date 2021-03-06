## Enable telnet/FTP/SSH in Kobo Aura ebook reader

This hack enables telnet/ftp/ssh on a new Kobo Aura reader. To install simply execute:

    ./package

And place the resulting KoboRoot.tgz file in the Kobo's partition that appears as you plug the reader to your computer. Place it in the directory named `.kobo`. Once there you can unplug the ereader's usb and restart the device.

Connect to the internet with your device by accessig the Kobo shop for example. Get the IP address of your device from the settings menu and while the WiFi is enabled. SSH into your device like so:

    ssh root@192.168.X.Y

The default password after this update will be `kobo!aura`. SSH refuses to let you in as root unless you have a password set.

### Using SSH keys for authentication
Plug your Kobo via USB to your computer and generate a keypair to give you passwordless access to your Kobo. You can use the script provided with this distribution for that. Just:

    ./sshkeypair

You will be prompted for a passphrase. You will have to enter this passphrase to open the key every time you ssh into your Kobo. You may leave this passphrase empty.

### Installing new authentication keys manually
Copy your public SSH key to the KOBOeReader directory where the device mounts in your system. Name the public key file `key.pub`. Restart the device, the key file will be automatically installed and it will be recognized the next time you log in.

Tested on firmware version 3.15.0 (April 2015)

[Direct links to Kobo official firmware](http://www.mobileread.com/forums/showthread.php?t=185660)
