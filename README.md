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
### OUTPUT

![alt text](images/1_cat_file1.png)

cat < file2
### OUTPUT

![alt text](images/2_cat_file2.png)
## Comparing Files
cmp file1 file2
### OUTPUT
![alt text](images/3_cmp.png) 

comm file1 file2
### OUTPUT

![alt text](images/4_comm.png)

diff file1 file2
### OUTPUT

![diff](images/5_diff.png)

### Filters

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
### OUTPUT

![cutfile11](images/6_cut_file11.png)

cut -d "|" -f 1 file22

### OUTPUT

![cut_file22](images/7_cut_file22.png)

cut -d "|" -f 2 file22

### OUTPUT
![cut_file22_2](images/6_1cut_file2.png)
cat > newfile 
```
Hello world
hello world
^d
```

grep Hello newfile 

### OUTPUT
![grep_Hello_newfile](images/8_grep_Hello_newfile.png)


grep hello newfile 
### OUTPUT

![alt text](images/9_grep_hello_newfile.png)


grep -v hello newfile 

### OUTPUT

![alt text](images/10_grep_v_hello_newfile.png)

cat newfile | grep -i "hello"
### OUTPUT

![alt text](images/11_cat_grep_hello_new_file.png)


cat newfile | grep -i -c "hello"
### OUTPUT

![alt text](images/12_cat_grep_count.png)


grep -R ubuntu /etc
### OUTPUT

![alt text](images/13_grep_R_ubuntu_etc.png)

grep -w -n world newfile   
### OUTPUT

![alt text](images/14_grep_w_n_world_newfile.png)

cat > newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

egrep -w 'Hello|hello' newfile 
### OUTPUT



egrep -w '(H|h)ello' newfile 
### OUTPUT



egrep -w '(H|h)ell[a-z]' newfile 
### OUTPUT

![alt text](images/15_egrep.png)


egrep '(^hello)' newfile 
### OUTPUT

![alt text](images/16_egrep_2.png)

egrep '(world$)' newfile 
### OUTPUT

![alt text](images/17_egrep3.png)

egrep '(World$)' newfile 
### OUTPUT

![alt text](images/18_egrep_World.png)

egrep '((W|w)orld$)' newfile 
### OUTPUT

![alt text](images/19_egrep_Wworld.png)

egrep '[1-9]' newfile 
### OUTPUT

![alt text](images/20_egrep_1_9.png)

egrep 'Linux.*world' newfile 
### OUTPUT

![alt text](images/21_egrep_Linux.png)

egrep 'Linux.*World' newfile 
### OUTPUT

![alt text](images/22_egrep_linux.png)

egrep l{2} newfile
### OUTPUT

![alt text](images/23_egrep_ll.png)

egrep 's{1,2}' newfile
### OUTPUT 

![alt text](images/24_egrep_s.png)

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
^d
```


sed -n -e '3p' file23
### OUTPUT

![alt text](images/25_sed.png)

sed -n -e '$p' file23
### OUTPUT

![alt text](images/26_sed_p.png)

sed  -e 's/Ram/Sita/' file23
### OUTPUT

![alt text](images/27_sed_s_Ram_sita.png)

sed  -e '2s/Ram/Sita/' file23
### OUTPUT

![alt text](images/28_sed_2s_Ram_sita.png)

sed  '/tom/s/5000/6000/' file23
### OUTPUT

![alt text](images/29.png)

sed -n -e '1,5p' file23
### OUTPUT

![alt text](images/30_sed_e_1_5p.png)


sed -n -e '2,/Joe/p' file23
### OUTPUT

![alt text](images/31_sed_e_n_jeo.png)


sed -n -e '/tom/,/Joe/p' file23
### OUTPUT

![alt text](images/32_sed_tom_jeo.png)

seq 10 
### OUTPUT

![alt text](images/33_seq_10.png)
```
seq 10 | sed -n '4,6p'
seq 10 | sed -n '2,~4p'
seq 3 | sed '2a hello'
```
### OUTPUT

![alt text](images/34_seq1.png)\

```
seq 2 | sed '2i hello'
seq 10 | sed '2,9c hello'
sed -n '2,4{s/^/$/;p}' file23
sed -n '2,4{s/$/*/;p}' file23
```
### OUTPUT

![alt text](images/35_seq.png)


### Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
### OUTPUT
![alt text](images/36_sort.png)

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
### OUTPUT

![alt text](images/37_uniq.png)

### Using tr command

cat file23 | tr [:lower:] [:upper:]
### OUTPUT
![alt text](images/38_tr.png)

cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
 ```
cat urllist.txt | tr -d ' '
cat urllist.txt | tr -d ' ' | tr -s '.'
```
 ### OUTPUT

![alt text](images/39_tr.png)


### Backup commands
tar -cvf backup.tar *
### OUTPUT

![alt text](images/40_tar.png)
```
mkdir backupdir
mv backup.tar backupdir
tar -tvf backup.tar
```
### OUTPUT

![alt text](images/41_tar.png)

tar -xvf backup.tar
### OUTPUT
![alt text](images/42_tar_x.png)
```
gzip backup.tar
ls .gz
```
### OUTPUT
![alt text](images/43_gzip.png)

gunzip backup.tar.gz
### OUTPUT
![alt text](images/44_gunzip.png)
 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0' >> my-script.sh
chmod 755 my-script.sh
./my-script.sh
```
### OUTPUT

cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
### OUTPUT

![alt text](images/46_heredoc.png)

cat > scriptest.sh 
```bash
#!/bin/sh
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

### OUTPUT
![alt text](images/47_script_test.png)
 
 
### mis-using string comparisons

cat > strcomp.sh 
```bash
#!/bin/bash
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
chmod 755 strcomp.sh
 
./strcomp.sh 
### OUTPUT

![alt text](images/48_strcompsh.png)
###  check file ownership
cat > psswdperm.sh 
```bash
#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

./psswdperm.sh
### OUTPUT
![alt text](images/49_passwdpermsh.png)

###  check if with file location
cat > ifnested.sh 
```bash
#!/bin/bash
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
$ chmod 755 ifnested.sh
 
$ ./ifnested.sh

### OUTPUT
![alt text](images/50_ifnested.png)

### looking for a possible value using elif
cat > elifcheck.sh 
```bash
#!/bin/bash
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

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
### OUTPUT
![alt text](images/51_elifcheck.png)

### testing compound comparisons
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
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
### OUTPUT

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
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
 
### OUTPUT
![alt text](images/52_casechech.png)

# RESULT:
The Commands are executed successfully.
