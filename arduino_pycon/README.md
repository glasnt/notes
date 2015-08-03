Some small notes from the event: 

Website: http://py-ardx.com/

### Installation for Ubuntu: 

executing arduino IDE - download tar.xz, extract, `sudo ./arduino`. Requires elevated permissions
 * installing firmata - `Ctrl-U`, upload in 1.6.3 is no longer under `File`

### TTY Permissions
By default, I was getting errors to the tune of "Unable to find serial port", even though things were plugged in. 

Cause: `/dev/ttyACM0` did not have the right permissions  

Solution: http://askubuntu.com/questions/58119/changing-permissions-on-serial-port
 * `sudo usermod -a -G dialout USERNAME`
 * logout and log back in again
