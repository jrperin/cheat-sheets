# Shell

## Script Infos

``` bash
# Location Variables
ME=`basename "$0"`
SCRIPT=`realpath $0`
SCRIPTPATH=`dirname $SCRIPT`

# RESULT:

# get_flags.sh
# /home/jrperin/projetos/freelancer/chromium-harika/get_flags/get_flags.sh
# /home/jrperin/projetos/freelancer/chromium-harika/get_flags

```

## Command Line Parameters
``` bash
if [ "$#" -lt "1" ]; then
    echo
    echo "You need to inform the chromium full path directory"
    echo
    echo "Example:"
    echo "bash $ME /home/some_paths/chromium/"
    echo
    exit 12
fi
```

## Convert to Lower Case
``` bash
result="Teste"
result=$(echo $result | tr '[A-Z]' '[a-z]') # To lowercase
```

## Read Data From Terminal
``` bash
echo "This will recreate all Microservices containers."
read -p "Continue? Y/[N]: " result
result="${result:=N}"
result=$(echo $result | tr '[A-Z]' '[a-z]') # To lowercase
```

## Check If Directory Exists
```bash
DIR="/etc/httpd/"
if [ -d "$DIR" ]; then
  echo "Dirctory ${DIR} exists..."
fi
```

## Recursive Finder
``` bash
grep --color=none -rFhHoa -f $SCRIPTPATH/patterns.txt --exclude=switches.{cc,h} --exclude-dir=.git ./ | awk -F:  '{print $1 "," $2}'  > $OUTPUTFILE1

# RESULT:

# head 2_lines_with_flags_no_duplicates.csv 
# ./dbus/values_util_unittest.cc,kV
# ./dbus/bus.cc,kTimeout
# ./build/android/gradle/android.jinja,kVersion
# ./build/android/gradle/generate_gradle.py,kVersion
# ./build/android/CheckInstallApk-debug.apk,kV
# ./build/android/incremental_install/installer.py,kHelp

```

## Removing Duplicates

``` bash
awk '!x[$0]++' $OUTPUTFILE1 > $OUTPUTFILE2

# RESULT:

# $OUTPUTFILE1 ------------------------------
# head 1_lines_with_flags.csv 
# ./dbus/values_util_unittest.cc,kV
# ./dbus/values_util_unittest.cc,kV
# ./dbus/values_util_unittest.cc,kV
# ./dbus/values_util_unittest.cc,kV
# ./dbus/bus.cc,kTimeout
# ./dbus/bus.cc,kTimeout

# $OUTPUTFILE2 ------------------------------
# head 2_lines_with_flags_no_duplicates.csv 
# ./dbus/values_util_unittest.cc,kV
# ./dbus/bus.cc,kTimeout

```

## SCP

``` bash
scp -i path_to_private_key deploy.zip user@server_ip:~
```

## SSH Sudo in Remote Command

``` bash
ssh -i path_to_private_key -t user@server_ip 'sudo bash -c "mkdir -p /root/mining/ ; cp deploy.zip /root/mining" '
```

## Replace String
``` bash
echo "Welcome To Linuxhint" | tr [:space:] '\n'

echo "Python is a Programming language" | tr -d 'Pyt'

cat portas_ms.txt | grep -e ")" -e "PORT" | xargs -n 3 echo | tr -d ")" | awk '{ print $1";" $3 }'| tr -d "PORT="
```
