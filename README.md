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
![cat-file1](./imgs/cat-file1.png)



cat < file2
## OUTPUT
![catfile2](./imgs/catfile2.png)


# Comparing Files
cmp file1 file2
## OUTPUT
![cmp](./imgs/cmp.png)
 
comm file1 file2
 ## OUTPUT
 ![comm](./imgs/comm.png)

 
diff file1 file2
## OUTPUT
![diff](./imgs/diff.png)

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
![file11](./imgs/file11.png)
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```
![file22](./imgs/file22.png)


cut -c1-3 file11
## OUTPUT
![cutfile11](./imgs/cutfile11.png)



cut -d "|" -f 1 file22
## OUTPUT
![cutfile22](./imgs/cutfile22.png)


cut -d "|" -f 2 file22
## OUTPUT
![cutfile22(2)](./imgs/cutfile22(2).png)


cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
```
Hello world
hello world
```
![catNewFile](./imgs/catNewFile.png)

 
grep Hello newfile 
## OUTPUT
![grepHello](./imgs/grepHello.png)



grep hello newfile 
## OUTPUT
![grephello](./imgs/grephello.png)




grep -v hello newfile 
## OUTPUT
![grep-v-hello](./imgs/grep-v-hello.png)



cat newfile | grep -i "hello"
## OUTPUT
![grep-i](./imgs/grep-i.png)




cat newfile | grep -i -c "hello"
## OUTPUT
![grep-i-c](./imgs/grep-i-c.png)




grep -R ubuntu /etc
## OUTPUT

![grep-ubuntu](./imgs/grep-ubuntu.png)




grep -w -n world newfile   
## OUTPUT
![grep-w-nworld](./imgs/grep-w-nworld.png)


cat > newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat <> newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
 ![newfile](./imgs/newfile.png)


egrep -w 'Hello|hello' newfile 
## OUTPUT
![Hello|hello-egrep](./imgs/Hello|hello-egrep.png)




egrep -w '(H|h)ello' newfile 
## OUTPUT
![H|h-egrep](./imgs/H|h-egrep.png)



egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![H|hella-z](./imgs/H|hella-z.png)




egrep '(^hello)' newfile 
## OUTPUT
![^hello](./imgs/^hello.png)



egrep '(world$)' newfile 
## OUTPUT
![world$](./imgs/world$.png)


egrep '(World$)' newfile 
## OUTPUT
![World$](./imgs/World$.png)


egrep '((W|w)orld$)' newfile 
## OUTPUT
![W|world$](./imgs/W|world$.png)



egrep '[1-9]' newfile 
## OUTPUT
![[1-9]](./imgs/[1-9].png)



egrep 'Linux.*world' newfile 
## OUTPUT
![Linux.*world](./imgs/Linux.*world.png)


egrep 'Linux.*World' newfile 
## OUTPUT
![Linux.*World](./imgs/Linux.*World.png)


egrep l{2} newfile
## OUTPUT
![l{2}](./imgs/l{2}.png)



egrep 's{1,2}' newfile
## OUTPUT 
![s{1,2}](./imgs/s{1,2}.png)


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
![file23](./imgs/file23.png)


sed -n -e '3p' file23
## OUTPUT
![sed3p](./imgs/sed3p.png)



sed -n -e '$p' file23
## OUTPUT
![sed$p](./imgs/sed$p.png)



sed  -e 's/Ram/Sita/' file23
## OUTPUT
![s-Ram-Sita-sed](./imgs/s-Ram-Sita-sed.png)



sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![2s-Ram-Sita-sed](./imgs/2s-Ram-Sita-sed.png)


sed  '/tom/s/5000/6000/' file23
## OUTPUT
![tom-5kto6k](./imgs/tom-5kto6k.png)




sed -n -e '1,5p' file23
## OUTPUT
![1to5file23](./imgs/1to5file23.png)



sed -n -e '2,/Joe/p' file23
## OUTPUT

![2-Joe-p](./imgs/2-Joe-p.png)



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![tom-to-Joe-sed](./imgs/tom-to-Joe-sed.png)



seq 10 
## OUTPUT
![seq10](./imgs/seq10.png)



seq 10 | sed -n '4,6p'
## OUTPUT
![4to6-seq](./imgs/4to6-seq.png)


seq 10 | sed -n '2,~4p'
## OUTPUT
![2-to-mul4-seq10](./imgs/2-to-mul4-seq10.png)




seq 3 | sed '2a hello'
## OUTPUT
![seq3-2ahello](./imgs/seq3-2ahello.png)



seq 2 | sed '2i hello'
## OUTPUT
![seq2-2ihello](./imgs/seq2-2ihello.png)


seq 10 | sed '2,9c hello'
## OUTPUT
![2to9c](./imgs/2to9c.png)


sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![2to4-s](./imgs/2to4-s.png)



sed -n '2,4{s/$/*/;p}' file23

![2to4-s*p](./imgs/2to4-s*p.png)


#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21s
## OUTPUT
![sort-file21](./imgs/sort-file21.png)


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
![uniq-file22](./imgs/uniq-file22.png)



#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
 ![lower-to-upper](./imgs/lower-to-upper.png)

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
 ![urllist](./imgs/urllist.png)


 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![rm-dots](./imgs/rm-dots.png)



#Backup commands
tar -cvf backup.tar *
## OUTPUT
![backup.tar](./imgs/backup.tar.png)
mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT
![tvfbackup](./imgs/tvfbackup.png)


tar -xvf backup.tar
## OUTPUT
![tar-xvf-backup](./imgs/tar-xvf-backup.png)


gzip backup.tar

ls *.gz
## OUTPUT
![ls*.gz](./imgs/ls*.gz.png)
 
gunzip backup.tar.gz
## OUTPUT
![gunzip-backup.tar.gz](./imgs/gunzip-backup.tar.gz.png)

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
![my-script](./imgs/my-script.png)

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
![herecheck](./imgs/herecheck.png)


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
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
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


![scriptest](./imgs/scriptest.png)


 
ls file1
## OUTPUT

![lsfile1](./imgs/lsfile1.png)


echo $?
## OUTPUT 
![echo](./imgs/echo.png)

./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 

![echoabcd](./imgs/echoabcd.png)
 
abcd
 
echo $?
 ## OUTPUT

![echoabcd](./imgs/echoabcd.png)
 
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
## OUTPUT

![strcomp-cat](./imgs/strcomp-cat.png)

chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT

![strcomp-cat](./imgs/strcomp-cat.png)

![strcomp.sh](./imgs/strcomp.sh.png)






# check file ownership
cat < psswdperm.sh 
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

cat psswdperm.sh 
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

![psswdperm](./imgs/psswdperm.png)



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
^d
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

![ifnested](./imgs/ifnested.png)

![ifnested.sh2](./images/ifnested.sh2.png)







# using numeric test comparisons
cat > iftest.sh 
```bash
#!/bin/bash
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

$ chmod 755 iftest.sh
 
$ ./iftest.sh 





## OUTPUT
![iftest](./imgs/iftest.png)



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

$ chmod 755 ifnested.sh

$ ./ifnested.sh 



## OUTPUT
![ifnested](./imgs/ifnested.png)

![ifnested2](./imgs/ifnested2.png)



# looking for a possible value using elif
cat elifcheck.sh 
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

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
![elifcheck](./imgs/elifcheck.png)

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
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![ifcompound](./imgs/ifcompound.png)

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



![casecheck](./imgs/casecheck.png)

 
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
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh


 ![whiletest](./imgs/whiletest.png)

 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 


 ![unttiltest](./imgs/unttiltest.png)

 
cat forin1.sh 
```bash
#!/bin/bash
#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh



 ![forin1.sh](./imgs/forin1.sh.png)

 
cat forin2.sh 
```bash
#!/bin/bash
# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh





 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 

![forin2](./imgs/forin2.png)
 
cat forin3.sh 
```bash
#!/bin/bash
# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 

![forin3.sh](./imgs/forin3.sh.png)
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh




## OUTPUT

![forin1.sh-cat](./imgs/forin1.sh-cat.png)


cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file"
done
```
$ chmod 777 forinfile.sh

$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam


## OUTPUT

![forinfile.sh](./imgs/forinfile.sh.png)


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh

$ ./forctype.sh

## OUTPUT
![forctype](./imgs/forctype.png)

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh

$ ./forctype1.sh 

## OUTPUT


![forctype](./imgs/forctype.png)


![forctype1.sh](./imgs/forctype1.sh.png)



cat fornested1.sh 
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
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 

 ## OUTPUT

 ![fornested1.sh](./imgs/fornested1.sh.png)

 
cat forbreak.sh 
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
## OUTPUT



![forbreak.sh](./imgs/forbreak.sh.png)


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
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
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 

## OUTPUT



![forcontinue.sh](./imgs/forcontinue.sh.png)

 
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 

## OUTPUT

![exread.sh](./imgs/exread.sh.png)



 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT



![exread1.sh](./imgs/exread1.sh.png)




$ ./exread1.sh 
 
cat funcex.sh
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

![funcex.sh](./imgs/funcex.sh.png)
 
 ./funcex.sh 1 2

 

 ![funcex12](./imgs/funcex12.png)


 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT

$ ./argshift.sh 1 2 3



![argshift](./imgs/argshift.png)

 
 cat argshift1.sh
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
$ chmod 777 argshift.sh

## OUTPUT

$ ./argshift.sh 1 2 3




![argshift1.sh](./imgs/argshift1.sh.png)






 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT

 ./argshift.sh 1 2 3

 
 

![argshift123](./imgs/argshift123.png)

 
 
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


![nc.awk](./imgs/nc.awk.png)


 
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
## OUTPUT 



![palyes](./imgs/palyes.png)
![palno](./imgs/palno.png)



# RESULT:
The Commands are executed successfully.
