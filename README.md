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
cat < file2
## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26](https://github.com/user-attachments/assets/5ce11d5e-b22b-4440-b437-402b3b5f2329)

# Comparing Files
cmp file1 file2
comm file1 file2
diff file1 file2

## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26 (1)](https://github.com/user-attachments/assets/47e54974-3c30-4f27-ba14-5262bbe7f1ac)

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
cut -d "|" -f 1 file22
cut -d "|" -f 2 file22
cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world





grep hello newfile 
grep -v hello newfile 
cat newfile | grep -i "hello"
cat newfile | grep -i -c "hello"
## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26 (2)](https://github.com/user-attachments/assets/cc67a173-d243-453b-9dc9-f4811d7a1628)




grep -R ubuntu /etc
## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26 (3)](https://github.com/user-attachments/assets/2e33b93b-e959-4fb9-8364-454453fae871)
![WhatsApp Image 2025-09-20 at 23 17 26 (4)](https://github.com/user-attachments/assets/8c20e05a-3135-423c-aac9-bfc4628613d2)



grep -w -n world newfile   
## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26 (5)](https://github.com/user-attachments/assets/dc776f1c-eb03-4818-a187-c16b92fcd51c)


cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

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
egrep -w '(H|h)ello' newfile 
egrep -w '(H|h)ell[a-z]' newfile 

![WhatsApp Image 2025-09-20 at 23 17 26 (5)](https://github.com/user-attachments/assets/dc776f1c-eb03-4818-a187-c16b92fcd51c)

egrep '(^hello)' newfile 
egrep '(world$)' newfile 
egrep '((W|w)orld$)' newfile 
egrep '[1-9]' newfile 
egrep 'Linux.*world' newfile 
egrep 'Linux.*World' newfile
egrep l{2} newfile
## OUTPUT
![WhatsApp Image 2025-09-20 at 23 17 26 (7)](https://github.com/user-attachments/assets/c5dd812a-8183-483f-8bad-57a3ae827226)



egrep 's{1,2}' newfile
## OUTPUT 
<img width="1015" height="80" alt="image" src="https://github.com/user-attachments/assets/096ba84a-0f4f-40c5-bf14-6aa5f8f9bd54" />


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
sed -n -e '$p' file23
sed  -e 's/Ram/Sita/' file23
## OUTPUT
<img width="942" height="577" alt="image" src="https://github.com/user-attachments/assets/d958a732-457e-4bf4-bf7c-b306b3863696" />



sed  -e '2s/Ram/Sita/' file23
sed  '/tom/s/5000/6000/' file23
sed -n -e '1,5p' file23
## OUTPUT
<img width="915" height="640" alt="image" src="https://github.com/user-attachments/assets/68f824c3-89a3-412d-8375-aa9627a5671b" />

sed -n -e '2,/Joe/p' file23
sed -n -e '/tom/,/Joe/p' file23
seq 10
seq 10 | sed -n '4,6p'
## OUTPUT
<img width="858" height="602" alt="image" src="https://github.com/user-attachments/assets/d562400d-2732-4038-810c-ee875ce26701" />

seq 10 | sed -n '2,~4p'
seq 3 | sed '2a hello'
seq 2 | sed '2i hello'
seq 10 | sed '2,9c hello'
sed -n '2,4{s/^/$/;p}' file23
sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
<img width="738" height="473" alt="image" src="https://github.com/user-attachments/assets/520cd714-8c92-403e-a46a-cd3c83279f38" />


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
<img width="893" height="160" alt="image" src="https://github.com/user-attachments/assets/26e22a78-f0b0-4486-916d-8de5b733ad83" />

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
#Using tr command
cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
<img width="835" height="662" alt="image" src="https://github.com/user-attachments/assets/d80c37fe-cf70-4391-9538-fdad75b10c82" />

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
<img width="603" height="117" alt="image" src="https://github.com/user-attachments/assets/c7dfcae0-c224-45b8-ac7e-3ac3180b6230" />

cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
<img width="720" height="141" alt="image" src="https://github.com/user-attachments/assets/62a43841-da86-4ff5-ab01-938db8881104" />

#Backup commands

mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT
<img width="797" height="248" alt="image" src="https://github.com/user-attachments/assets/78df38ce-b0b2-422b-a6bd-9cf51afe9c1c" />

tar -xvf backup.tar
## OUTPUT

gzip backup.tar

ls .gz
## OUTPUT
 
gunzip backup.tar.gz
## OUTPUT

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
<img width="340" height="65" alt="image" src="https://github.com/user-attachments/assets/47fd65d7-b023-41b2-b662-bd7de963771d" />

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
<img width="576" height="147" alt="image" src="https://github.com/user-attachments/assets/f6035cf6-1223-44ba-9f9e-7117492a093c" />


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
<img width="578" height="331" alt="image" src="https://github.com/user-attachments/assets/9687dcd0-f9ba-46a7-b4e5-06126670af80" />

 
ls file1
## OUTPUT
<img width="946" height="87" alt="image" src="https://github.com/user-attachments/assets/7fd2de74-7d49-44ea-b4c4-4dbb1c73c6eb" />

echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
 <img width="341" height="57" alt="image" src="https://github.com/user-attachments/assets/9a8bb2fd-e3e8-4325-8a86-b66640771859" />

abcd
 
echo $?
 ## OUTPUT
<img width="341" height="57" alt="image" src="https://github.com/user-attachments/assets/9d3a19c2-f6f2-42e3-86fa-3fa3f0cf0e68" />


 
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
<img width="491" height="52" alt="image" src="https://github.com/user-attachments/assets/e761b527-e74b-4218-9785-2210a4dd8d25" />

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
<img width="936" height="87" alt="image" src="https://github.com/user-attachments/assets/26d2b9aa-314c-4567-9541-3a64940e8382" />

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
<img width="1000" height="113" alt="image" src="https://github.com/user-attachments/assets/0ec04933-4a35-40e7-9588-41e4e3b6aa94" />



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

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
## OUTPUT

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
<img width="1055" height="142" alt="image" src="https://github.com/user-attachments/assets/5a249c0d-51b1-4ac0-b64f-692483c5280a" />


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
<img width="986" height="75" alt="image" src="https://github.com/user-attachments/assets/74d9e254-946a-4b89-8565-7bb376200e91" />


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
<img width="815" height="90" alt="image" src="https://github.com/user-attachments/assets/0a7ae990-1c1e-4d5c-9ac6-4693904bfb9f" />

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
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 
 
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
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
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
<img width="817" height="218" alt="image" src="https://github.com/user-attachments/assets/99015893-7335-4d4f-a78d-b3101df569ab" />


cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
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
<img width="345" height="166" alt="image" src="https://github.com/user-attachments/assets/a38d7e3b-5ac0-45d8-acfd-2f8af588a2f4" />


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
<img width="345" height="166" alt="image" src="https://github.com/user-attachments/assets/cf481edd-745f-4b92-a098-8c2cd689b831" />


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
<img width="347" height="171" alt="image" src="https://github.com/user-attachments/assets/a8461f71-ca93-4e72-a33e-a5208b087d64" />

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
<img width="342" height="355" alt="image" src="https://github.com/user-attachments/assets/31118fae-6cfa-4f5b-86f8-0af12748aab6" />

 
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
<img width="355" height="90" alt="image" src="https://github.com/user-attachments/assets/637b9707-f535-41e3-8963-ca449b1d46d0" />

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


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT



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
<img width="345" height="57" alt="image" src="https://github.com/user-attachments/assets/2f79f464-0eee-4a69-be6a-6ee07cc06724" />

 ./funcex.sh 

 
 ./funcex.sh 1 2

 
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
<img width="360" height="80" alt="image" src="https://github.com/user-attachments/assets/00eb36f1-7eb0-4824-9cd8-4a3940bc5b25" />

 ./argshift.sh 1 2 3
 
 
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
<img width="717" height="116" alt="image" src="https://github.com/user-attachments/assets/b6a60d5d-383c-48c2-b5ed-8b3f071900da" />


# RESULT:
The Commands are executed successfully.
