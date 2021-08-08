# Bandit

## level 0

username: bandit0
password: bandit0

## level 0 -> level 1

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit0
cat readme
```

got password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

## level 1 -> level 2

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit1
cat ./-
```

got password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9


## level 2 -> level 3

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit2
cat ./spaces\ in\ this\ filename
```

got password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

## level 3 -> level 4

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit3
ls -a
cd inhere
ls -a
cat .hidden
```

got password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB


## level 4 -> level 5

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit4
cd inhere
find . -type f | xargs file | grep text
```

got password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## level 5 -> level 6

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit5
cd inhere
find . -type f -size 1033c ! -executable | xargs file | grep text
```


got password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7


## level 6 -> level 7

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit6
find / -group bandit6 -user bandit7 -size 33c
```

got password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

Note: ugly solution. Had to find the file where persmission was not denied


## level 7 -> level 8

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit7
vim data.txt
/millionth
```

got password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## level 8 -> level 9

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit8
sort data.txt | uniq -c | grep '^ *1 '
```

got password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## level 9 -> level 10

**sollution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit9
strings data.txt | grep ==
```

got password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## level 10 -> level 11

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit10
strings data.txt | base64 --decode
```

got password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

## level 11 -> level 12

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit11
cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'
```

got password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu


## level 12 -> level 13

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit12
mdkir /tmpa/hoang
cp ./data.txt /tmp/hoang/
cd /tmp/hoang

cat data.txt | xxd -r data
file data
mv data data2.gz
gzip -d data2.gz
file data2
mv data2 data3.bz
bzip2 -d data3.bz
file data3
mv data3 data4.gz
gzip -d data4.gz
file data4
mv data4 data5.tar
tar -xf data5.tar
file data5.bin
mv data5.bin data6.tar
tar -xf data6.tar
file data6.bin
mv data6.bin data7.bz
bzip2 -d data7bz
file data7
mv data7 data8.tar
tar -xf data8.tar
mv data8.bin data9.gz
gzip -d data9.gz
cat data9
```

got password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

Note: this was stupidly long....


## level 13 -> level 14

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit13
ssh bandit14@localhost -i sshkey.private
cat /etc/bandit_pass/bandit14
```

got password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

## level 14 -> level 15

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit14
echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000
```

got password: BfMYroe26WYalil77FoDi9qh59eK5xNr

## level 15 -> level 16

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit15
openssl s_client -ign_eof -connect localhost:30001
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```

got password: cluFn7wTiGryunymYOu4RcffSxQluehd

Note: `s_client` implements a generic SSL/TLS client which can establish a transparent connection to a remote server speaking SSL/TLS. `openssl s_client` opens an SSL connection. The tag `-ign_eof` makes sure the connection is not closed immediately.

## level 16 -> level 17

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit16
nmap -p 31000-32000 localhost
openssl s_client -connect localhost:31790
```

got ssh key:

```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```

Save ssh key into a file. No write access in home folder

```
mkdir /tmp/key
cd /tmp/key
echo sshkey > ./sshkey.private
cmod 400 ./sshkey.private
ssh banidt17@localhost -i sshkey.private
cd /etc/bandit17
echo bandit17
```

got password: xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn

Note: you have to openssl to every port after nmap. Better solution could be found.

## level 17 -> level 18

**solutions**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit17
diff passwords.new passwords.old
```

got password: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

## level 18 -> level 19

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit18 "cat ~/readme"
```

got password: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

## level 19 -> level 20

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit19
./bandit20-do
./bandit20-do id
./bandit20-do cat /etc/bandit_pass/bandit20
```

got password: GbKksEFF4yrVs6il55v6gwY5aVje5f0j