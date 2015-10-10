While you're building tools for Tessel, you may need to access Tessel in ways not exposed by the CLI. Here are two options:

## SSH

If you can get your Tessel online, this is the easiest way to get root access to your Tessel.

### Setup

Make sure your Tessel is [online](http://tessel.github.io/t2-start/wifi.html). Check that it shows up on LAN with `t2 list`.

Run `t2 provision` to authorize your computer with your Tessel.

### SSH in

Use the command `ssh@<tesselname>.local -i ~/.tessel/id_rsa`.

The `-i` command lets you specify the filepath to the RSA keys written by `t2 provision`.

### Getting out

When you need out, type `exit`.

## dterm

Dterm lets you talk to Tessel over USB.

### Setup

Install dterm with `brew install dterm`.

Figure out what USB port your Tessel is plugged into by typing `ls /dev/tty.usbmodem` – see whether it auto-completes to e.g. `/dev/tty.usbmodem1412` or a different number.

### dterm in

Run `dterm /dev/tty.usbmodem1412` (or a different port number).
You will have to press enter twice.

If you're going to do this a lot, it might be a good idea to alias the command: `alias v2="dterm /dev/tty.usbmodem1412"`.

If you need your ip address (for example if you'd like to ssh in next time), you can run `ifconfig` to get it.

### Getting out

`CTRL+]`

then

`CTRL+C`
