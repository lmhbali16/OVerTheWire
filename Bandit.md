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
strings data.txt | grep ==
```

got password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## level 10 -> level 11

**solution**:

```
strings data.txt | base64 --decode
```

got password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

## level 11 -> level 12

**solution**:

```
cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'
```

got password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu