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


# level 13 -> level 14

**solution**:

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit13
ssh bandit14@localhost -i sshkey.private
cat /etc/bandit_pass/bandit14
```

got password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

# level 14 -> level 15

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit14
echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000
```

got password: BfMYroe26WYalil77FoDi9qh59eK5xNr

# level 15 -> level 16

**solution**

```
ssh bandit.labs.overthewire.org -p 2220 -l bandit15
openssl s_client -ign_eof -connect localhost:30001
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```

got password: cluFn7wTiGryunymYOu4RcffSxQluehd

Note: `s_client` implements a generic SSL/TLS client which can establish a transparent connection to a remote server speaking SSL/TLS. `openssl s_client` opens an SSL connection. The tag `-ign_eof` makes sure the connection is not closed immediately.

