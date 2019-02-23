# gentoo-notes
Some notes for my gentoo setup

## Plymouth
### Fallback to text mode
```
> mv /lib/udev/rules.d/71-udev-seat.rules /lib/udev/rules.d/71-seat.rules
```
Turns out the seat rules were in a different file then genkernel expects them.

That leads to udev not tagging the card as seat and plymouth on boot failing as no seat was detected
