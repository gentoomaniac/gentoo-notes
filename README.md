# gentoo-notes
Some notes for my gentoo setup

## Plymouth
### Fallback to text mode
```
> mv /lib/udev/rules.d/71-udev-seat.rules /lib/udev/rules.d/71-seat.rules
```
Turns out the seat rules were in a different file then genkernel expects them.

That leads to udev not tagging the card as seat and plymouth on boot failing as no seat was detected

## Suspend to RAM now working
```
> cat /sys/bus/usb/devices/*/power/wakeup
enabled
disabled
disabled
disabled
> cat /sys/bus/usb/devices/1-4/power/wakeup
enabled
> echo disabled | sudo tee /sys/bus/usb/devices/1-4/power/wakeup
disabled
```
This solved the issue as a work around. however this prevents the laptop from waking up by pressing any button.
To wake up you'll need to close and open the lid.
