# For mac OS user

To execute `virtctl vnc <my-window-machine>` you need to create a remote-viewer executable.

Install realvnc https://www.realvnc.com/en/connect/download/viewer/macos/

create a remote-viewer shell script
```
sudo cat<<EOF > /usr/local/bin/remote-viewer
#!/bin/bash
REAL_VNC="/Applications/VNC Viewer.app/Contents/MacOS/vncviewer"
HOSTPORT=\${1//vnc:\/\/}
"\${REAL_VNC}" -WarnUnencrypted=0 \${HOST_PORT}
EOF
chmod +x /usr/local/bin/remote-viewer
```