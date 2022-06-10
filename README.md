# autoplank

Use plank on multi-monitor setup without creating multiple docks. Simply move the mouse to the bottom of any monitor and plank moves there.


Original repo : https://github.com/abiosoft/autoplank

Current repo : Here I have added some un merged PR patches so we don't have to repeate that process each time, Also I have added pre build binary so you can directly use that without building...

## Usage

Start from the CLI.
```
autoplank
```

## Building/Installing

Requires Go 1.8 or newer.

Install Go using:

```
sudo apt install git golang-go xdotool
```

Then build:

```
make install
```

### [Optional] Create a service

You may want to create a service to start and keep running in background for convenience.

* create a systemd unit file `$HOME/.config/systemd/user/autoplank.service`

```ini
[Unit]
Description=Autoplank Service

[Service]
ExecStart=/usr/local/bin/autoplank
Restart=always

[Install]
WantedBy=graphical.target
```
* enable and start
```
systemctl enable autoplank --user
systemctl start autoplank --user
```
