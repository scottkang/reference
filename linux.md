# Exit code
$?
128 + N = signal N으로 종료
137 = 128 + 9

# if then
```shell
#!/bin/sh
num=10
if [ $num == 10 ]
then
    echo "Match"
fi
num=10
if [ $num -eq 10 ]
then
    echo "Match"
fi
```
If not enclosed with [], $num replaced with 10, and treated as a command - 10: command not found 

# $()
The contents in the parenthesis is treated as command and arguments
```shell
start_time=`date +%s`
sleep 1
end_time=`date +%s`

seconds=`expr $end_time - $start_time`
echo "Execution time is $(expr $end_time - $start_time) seconds"
```
# Timezone command
```bash
$>tzselect
Please identify a location so that time zone rules can be set correctly.
Please select a continent or ocean.
 1) Africa
 2) Americas
 3) Antarctica
 4) Arctic Ocean
 5) Asia
 6) Atlantic Ocean
 7) Australia
 8) Europe
 9) Indian Ocean
10) Pacific Ocean
11) none - I want to specify the time zone using the Posix TZ format.
#? 5
Please select a country.
 1) Afghanistan		  18) Israel		    35) Palestine
 2) Armenia		  19) Japan		    36) Philippines
 3) Azerbaijan		  20) Jordan		    37) Qatar
 4) Bahrain		  21) Kazakhstan	    38) Russia
 5) Bangladesh		  22) Korea (North)	    39) Saudi Arabia
 6) Bhutan		  23) Korea (South)	    40) Singapore
 7) Brunei		  24) Kuwait		    41) Sri Lanka
 8) Cambodia		  25) Kyrgyzstan	    42) Syria
 9) China		  26) Laos		    43) Taiwan
10) Cyprus		  27) Lebanon		    44) Tajikistan
11) East Timor		  28) Macau		    45) Thailand
12) Georgia		  29) Malaysia		    46) Turkmenistan
13) Hong Kong		  30) Mongolia		    47) United Arab Emirates
14) India		  31) Myanmar (Burma)	    48) Uzbekistan
15) Indonesia		  32) Nepal		    49) Vietnam
16) Iran		  33) Oman		    50) Yemen
17) Iraq		  34) Pakistan
#? 23

The following information has been given:

	Korea (South)

Therefore TZ='Asia/Seoul' will be used.
Local time is now:	Thu Jan  4 16:14:14 KST 2024.
Universal Time is now:	Thu Jan  4 07:14:14 UTC 2024.
Is the above information OK?
1) Yes
2) No
#? 1  

You can make this change permanent for yourself by appending the line
	TZ='Asia/Seoul'; export TZ
to the file '.profile' in your home directory; then log out and log in again.

Here is that TZ value again, this time on standard output so that you
can use the /bin/tzselect command in shell scripts:
Asia/Seoul
```

# firewall-cmd
```bash
firewall-cmd --zone=public --add-port 18080/tcp
```

# selinux
```bash
$>sestatus
$>setenforce 0
$>semanage port -l
$>semanage port -a -t http_port_t -p tcp 18080
```
