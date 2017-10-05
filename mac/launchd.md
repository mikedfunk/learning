# Launchd Services

You can create a script that runs on startup and tries to restart when it fails. Just put this in `~/Library/LaunchAgents/com.my-script.whatever.plist`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>

	<key>KeepAlive</key>
	<true/>
  
	<key>Label</key>
	<string>com.my-script.whatever</string>
  
	<key>ProgramArguments</key>
	<array>
    <!-- example of command with arguments -->
		<string>/usr/local/bin/autossh</string>
		<string>-M</string>
		<string>0</string>
		<string>-t</string>
		<string>-N</string>
		<string>my-ssh-proxy-server</string>
	</array>
  
	<key>RunAtLoad</key>
	<true/>
  
  <!-- for debugging if something is not working -->
	<key>StandardErrorPath</key>
	<string>/tmp/myservice-stderr.log</string>
	<key>StandardOutPath</key>
	<string>/tmp/myservice-stdout.log</string>
  
</dict>
</plist>
```

and run 
```sh
launchctl load ~/Library/LaunchAgents/com.myscript.whatever.plist
```
(You can also `unload`) Since it is in (or symlinked into) the `LaunchAgents` folder, it will start on startup. Neat!
