# LenovoBatteryLinux
Battery Management for Ideapads(tested on Lenovo G580)

# Reference
[This page on lenovo forums](https://forums.lenovo.com/t5/Other-Linux-Discussions/ideapad-linux-acpi-driver-for-power-managment/td-p/2267447)

## Usage

On most distros acpi_call is probably available through your package manager, otherwise:

If you're using older ubuntu, please remove this line from installer
```
 cd acpi_call && sed -i 's|acpi/acpi.h|linux/acpi.h|' acpi_call.c && cd ../
```
And then, execute this command
`./install_acpi_call.sh`

After installing acpi_call module you can configure battery charge by executing main script

`./battery_management.sh`

## Raw commands: Set battery to 60% charging threshold

`# echo '\_SB.PCI0.LPCB.EC0.VPC0.SBMC 4' > /proc/acpi/call`
