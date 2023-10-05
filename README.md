# frida-ios-dump
Pull a decrypted IPA from a jailbroken device

## Usage

 1. Install [frida](http://www.frida.re/) on device
 2. `sudo pip install -r requirements.txt --upgrade`
 3. Run usbmuxd/iproxy SSH forwarding over USB (Default 2222 -> 22). e.g. `iproxy 2222 22`
 4. Run ./frida-ios-dump.py `Display name` or `Bundle identifier`
 5. Optionally copy `frida-ios-dump` and `frida-ios-dump.js` to your `/usr/local/bin` to avoid the hassle

```bash
~$ sudo cp frida-ios-dump* /usr/local/bin
```

For SSH/SCP make sure you have your public key added to the target device's ~/.ssh/authorized_keys file.

Start the target app YOUR_APP_NAME on your device

```bash
~$ frida-ios-dump -H 192.168.1.33 -p 22 -u root -P alpine YOUR_APP_NAME

Generating YOUR_APP_NAME.ipa

Done.
```

You can also list installed apps and processes via `--list` or `--process` args.

Drag to [MonkeyDev](https://github.com/AloneMonkey/MonkeyDev), Happy hacking!

## Support

Python 3.x

### issues

If the following error occurs:

* causes device to reboot
* lost connection
* unexpected error while probing dyld of target process

**NOTE:** Please open the application before dumping.
