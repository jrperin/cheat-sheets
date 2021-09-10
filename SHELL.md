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

# Removing Duplicates

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