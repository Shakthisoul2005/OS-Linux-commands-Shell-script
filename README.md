# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:

cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```

### Display the content of the files

cat < file1
## OUTPUT
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```

cat < file2
## OUTPUT
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
```

# Comparing Files
cmp file1 file2
## OUTPUT
```
keerthivasan@Aizen:~$ cmp file1 file2
file1 file2 differ: byte 1, line 1
```
 
comm file1 file2
 ## OUTPUT
```
keerthivasan@Aizen:~$ comm file1 file2

        anil aggarwal
        barun sengupta
                c.k. shukla
chanchal singhvi
        lalit chowdury
                s.n. dasgupta
sumit chakrobarty
```

diff file1 file2
## OUTPUT
```
keerthivasan@Aizen:~$ diff file1 file2
1c1,2
<
---
> anil aggarwal
> barun sengupta
3c4
< chanchal singhvi
---
> lalit chowdury
5d5
< sumit chakrobarty
```

#Filters
### Create the following files file11, file22 as follows:
cat > file11
```
Hello world
This is my world
^d
```

cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```

cut -c1-3 file11
## OUTPUT
```
keerthivasan@Aizen:~$ cut -c1-3 file11
Hel
Thi
```

cut -d "|" -f 1 file22
## OUTPUT
```
keerthivasan@Aizen:~$  cut -d "|" -f 1 file22
1001
1001
1002
1003
1005
1004
```

cut -d "|" -f 2 file22
## OUTPUT
```
keerthivasan@Aizen:~$ cut -d "|" -f 2 file22
 Ram
 Ram
 tom
 Joe
 Sam
 Sit
```

cat > newfile 
```
Hello world
hello world
````
cat < newfile 
```
Hello world
hello world
```
 
grep Hello newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ grep Hello newfile
Hello world
```

grep hello newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ grep hello newfile
hello world
```

grep -v hello newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ grep hello newfile
hello world
```

cat newfile | grep -i "hello"
## OUTPUT
```
keerthivasan@Aizen:~$ cat newfile | grep -i "hello"
Hello world
hello world
```

cat newfile | grep -i -c "hello"
## OUTPUT
```
keerthivasan@Aizen:~$ cat newfile | grep -i -c "hello"
2
```

grep -R ubuntu /etc
## OUTPUT
```

```

grep -w -n world newfile   
## OUTPUT
```
keerthivasan@Aizen:~$ grep -w -n world newfile
1:Hello world
2:hello world
```

cat > newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
```

cat < newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
 ```

egrep -w 'Hello|hello' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep -w 'Hello|hello' newfile
Hello world
hello world
```

egrep -w '(H|h)ello' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep -w '(H|h)ello' newfile
Hello world
hello world
```

egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep -w '(H|h)ell[a-z]' newfile
Hello world
hello world
```

egrep '(^hello)' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep '(^hello)' newfile
hello world
```

egrep '(world$)' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep '(world$)' newfile
Hello world
hello world
```

egrep '(World$)' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep '(World$)' newfile
Linux is best in this World
```

egrep '((W|w)orld$)' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep '((W|w)orld$)' newfile
Hello world
hello world
Linux is best in this World
```

egrep '[1-9]' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep '[1-9]' newfile
Linux is world number 1
```

egrep 'Linux.*world' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep 'Linux.*world' newfile
Linux is world number 1
```

egrep 'Linux.*World' newfile 
## OUTPUT
```
keerthivasan@Aizen:~$ egrep 'Linux.*World' newfile
Linux is best in this World
```

egrep l{2} newfile
## OUTPUT
```
keerthivasan@Aizen:~$ egrep l{2} newfile
Hello world
hello world
```

egrep 's{1,2}' newfile
## OUTPUT 
```
keerthivasan@Aizen:~$ egrep 's{1,2}' newfile
Linux is world number 1
Unix is predecessor
Linux is best in this World
```

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```

sed -n -e '3p' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n -e '3p' file23
1002 | tom |  5000 | Admin
```

sed -n -e '$p' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n -e '$p' file23
1001 | Ram | 10000 | HR
```

sed  -e 's/Ram/Sita/' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed  -e 's/Ram/Sita/' file23
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR
```


sed  -e '2s/Ram/Sita/' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed  -e '2s/Ram/Sita/' file23
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```

sed  '/tom/s/5000/6000/' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed  '/tom/s/5000/6000/' file23
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```

sed -n -e '1,5p' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n -e '1,5p' file23
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```

sed -n -e '2,/Joe/p' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n -e '2,/Joe/p' file23
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n -e '/tom/,/Joe/p' file23
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

seq 10 
## OUTPUT
```
keerthivasan@Aizen:~$ seq 10
1
2
3
4
5
6
7
8
9
10
```

seq 10 | sed -n '4,6p'
## OUTPUT
```
keerthivasan@Aizen:~$ seq 10 | sed -n '4,6p'
4
5
6
```

seq 10 | sed -n '2,~4p'
## OUTPUT
```
keerthivasan@Aizen:~$ seq 10 | sed -n '2,~4p'
2
3
4
```

seq 3 | sed '2a hello'
## OUTPUT
```
keerthivasan@Aizen:~$ seq 3 | sed '2a hello'
1
2
hello
3
```

seq 2 | sed '2i hello'
## OUTPUT
```
keerthivasan@Aizen:~$ seq 2 | sed '2i hello'
1
hello
2
```

seq 10 | sed '2,9c hello'
## OUTPUT
```

```

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
keerthivasan@Aizen:~$ sed -n '2,4{s/^/$/;p}' file23
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
$1003 | Joe |  7000 | Developer
```

#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
```
keerthivasan@Aizen:~$ sort file21
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR
```

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```

uniq file22
## OUTPUT
```
keerthivasan@Aizen:~$ uniq file22
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```

#Using tr command
cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
```
keerthivasan@Aizen:~$ cat file23 | tr [:lower:] [:upper:]
1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR
```

cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```

cat urllist.txt | tr -d ' '
 ## OUTPUT
```
keerthivasan@Aizen:~$ cat urllist.txt | tr -d ' '
www.yahoo.com
www.google.com
www.mrcet....com
```

cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
```
www.mrcet....com
keerthivasan@Aizen:~$ cat urllist.txt | tr -d ' ' | tr -s '.'
www.yahoo.com
www.google.com
www.mrcet.com
```

#Backup commands
tar -cvf backup.tar *
## OUTPUT
```
keerthivasan@Aizen:~$ tar -cvf backup.tar *
backupdir/
file
file1
file11
file2
file21
file22
file23
newfile
saveetha/
saveetha/fie1
saveetha/file1
saveetha/SEC/
trail/
trail/file1
urllist.txt
```

mkdir backupdir
mv backup.tar backupdir
tar -tvf backup.tar
## OUTPUT
```

```

tar -xvf backup.tar
## OUTPUT
```

```

gzip backup.tar
ls .gz
## OUTPUT
```

```

gunzip backup.tar.gz
## OUTPUT
```

```
 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘
```

chmod 755 my-script.sh
./my-script.sh
## OUTPUT
```
keerthivasan@Aizen:~$ chmod 755 my-script.sh
keerthivasan@Aizen:~$ ./my-script.sh
keerthivasan@Aizen:~$
```
 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
```
 hello in this world
i cant stop
for this non stop movement
```

cat > scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
```
keerthivasan@Aizen:~$ chmod 777 scriptest.sh
keerthivasan@Aizen:~$ ./scriptest.sh 1 2 3
./scriptest.sh: line 1: #!/bin/sh: No such file or directory
“File name is ./scriptest.sh ”
File name is  scriptest.sh
“First arg. is ” 1
“Second arg. is ” 2
“Third arg. is ” 3
“Fourth arg. is ”
The $@ is  1 2 3
The $\# is  1#
The $$ is  460
    PID TTY          TIME CMD
    425 pts/0    00:00:00 bash
    460 pts/0    00:00:00 bash
    463 pts/0    00:00:00 ps
```
 
ls file1
## OUTPUT
```
keerthivasan@Aizen:~$ ls file1
file1
```

echo $?
## OUTPUT 
```
keerthivasan@Aizen:~$ echo $?
0
```
 
# mis-using string comparisons
cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```

chmod 755 strcomp.sh
 ./strcomp.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ chmod 755 strcomp.sh
keerthivasan@Aizen:~$ ./strcomp.sh
baseball is less than hockey
```

# check file ownership
cat > psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat < psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
```
keerthivasan@Aizen:~$ sh psswdperm.sh
psswdperm.sh: 1: #!/bin/bash: not found
“Sorry, you are not the owner of the /etc/passwd file”
```

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ sh ifnested.sh
ifnested.sh: 1: #!/bin/bash: not found
“/home/keerthivasan The object exists, is it a file?”
“No,/home/keerthivasan it is not a file!”
“But /home/keerthivasan/.bash_history is a file!”
```

# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```

cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

chmod 755 iftest.sh
./iftest.sh 
##OUTPUT
```
keerthivasan@Aizen:~$ ./iftest.sh
./iftest.sh: line 1: #!/bin/bash: No such file or directory
“The test value 10 is greater than 5”
“The values are different”
```

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

# looking for a possible value using elif
cat > elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

chmod 755 elifcheck.sh
 
./elifcheck.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./elifcheck.sh
./elifcheck.sh: line 1: #!/bin/bash: No such file or directory
Sorry, you are not allowed here
```

# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```

chmod 755 ifcompound.sh
./ifcompound.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./ifcompound.sh
./ifcompound.sh: line 1: #!/bin/bash: No such file or directory
The file exists and you can write to it
```

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```

chmod 755 casecheck.sh 
./casecheck.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./casecheck.sh
Sorry, you are not allowed here
```
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```

chmod 755 whiletest.sh
./whiletest.sh
 ## OUTPUT
 ```
keerthivasan@Aizen:~$ ./whiletest.sh
10
9
8
7
6
5
4
3
2
1
```
 
cat > untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 

chmod 755 untiltest.sh 
./untiltest.sh
## OUTPUT
```
keerthivasan@Aizen:~$ ./untiltest.sh
./untiltest.sh: line 1: #using: command not found
100
75
50
25
``` 
 
cat >forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
chmod 755 forin1.sh
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
chmod 755 forin1.sh 
./forin1.sh
## OUTPUT
```
keerthivasan@Aizen:~$ ./forin1.sh
./forin1.sh: line 1: #!/bin/bash: No such file or directory
./forin1.sh: line 2: #basic: command not found
The next state is Alabama
The next state is Alaska
The next state is Arizona
The next state is Arkansas
The next state is California
The next state is Colorado
```
 
cat > forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```

chmod 755 forin2.sh
./forin2.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./forin2.sh
./forin2.sh: line 1: #!/bin/bash: No such file or directory
./forin2.sh: line 2: #: command not found
“word:I”
“word:dont know if thisll”
“word:work”
```
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```

chmod 755 forin3.sh
./forin3.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./forin3.sh
./forin3.sh: line 1: #!/bin/bash: No such file or directory
./forin3.sh: line 2: #: command not found
word:I
word:don't
word:know
word:if
word:this'll
word:work
```

cat > forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```

cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

chmod 777 forinfile.sh
./forinfile.sh
## OUTPUT
```
keerthivasan@Aizen:~$ ./forinfile.sh
 Visit beautiful cities
```

cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````

chmod 755 forctype.sh
./forctype.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./forctype.sh
The value of i is 1
The value of i is 2
The value of i is 3
The value of i is 4
The value of i is 5
```

cat > forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```

chmod 755 forctype.sh
./forctype1.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./forctype1.sh
1 - 5
2 - 4
3 - 3
4 - 2
5 - 1
```

cat > fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```

chmod 755 fornested1.sh
./fornested1.sh 
 ## OUTPUT
```
keerthivasan@Aizen:~$ ./fornested1.sh
Starting loop 1:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 2:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 3:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
```
 
cat > forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

chmod 755 forbreak.sh
./forbreak.sh 
## OUTPUT
```
 keerthivasan@Aizen:~$ ./forbreak.sh
Iteration number: 1
Iteration number: 2
The for loop is completed�
```

cat forcontinue.sh
```
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed"
```

chmod 755 forcontinue.sh
./forcontinue.sh
## OUTPUT
```
keerthivasan@Aizen:~$ ./forcontiune.sh
Iteration number: 1
Iteration number: 2
Iteration number: 4
Iteration number: 5
The for loop is completed
```

cat > exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
chmod 755 exread.sh 
./exread.sh 
## OUTPUT
```
keerthivasan@Aizen:~$ ./exread.sh
Enter your name: Keerthivasan
Hello Keerthivasan, welcome to my program.
```

cat >exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
chmod 755 exread1.sh 
./exread1.sh 
## OUTPUT
 ```
keerthivasan@Aizen:~$ ./exread1.sh
Enter your name: Keerthivasan
Hello Keerthivasan, welcome to my program.
```

cat > funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT

./funcex.sh 
```
keerthivasan@Aizen:~$ ./funcex.sh
Usage: badtest1 a b
```
./funcex.sh 1 2
```
keerthivasan@Aizen:~$ ./funcex.sh 1 2
The result is func 1 2
```
 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```

chmod 777 argshift.sh
./argshift.sh 1 2 3
## OUTPUT
```
keerthivasan@Aizen:~$ ./argshift.sh 1 2 3
1
2
3
```

cat > argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```

chmod 777 argshift.sh
./argshift.sh 1 2 3
## OUTPUT
```
keerthivasan@Aizen:~$ ./argshift.sh 1 2 3
1
2
3
```
  
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```

cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```

awk -f nc.awk data.dat
## OUTPUT 
 ```
keerthivasan@Aizen:~$ awk -f nc.awk data.dat
7        bcdfghj
8        abcdfghj
7        bcdfghj
8        ebcdfghj
7        bcdfghj
8        ibcdfghj
7        bcdfghj
8        obcdfghj
7        bcdfghj
8        ubcdfghj
total characters 75
Number of Lines are 10
No of Words count: 10
```

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
chmod 755 palindrome.sh
./palindrome.sh 
## OUTPUT 
```
keerthivasan@Aizen:~$ ./palindrome.sh
Enter the number
357
Number is NOT palindrome
```

# RESULT:
The Commands are executed successfully.
