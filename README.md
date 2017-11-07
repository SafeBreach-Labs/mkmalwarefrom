# mkmalwarefrom

mkmalwarefrom is a proof-of-concept two-stage dropper generator. It was released as part of the [Malwares From Thin Bits](http://www.securitybsides.com/w/page/118353951/DFW_2017) talk given at BSidesDFW 2017 conference by Itzik Kotler from [SafeBreach Labs](http://www.safebreach.com).

Slides are availble [here](http://www.ikotler.org/MalwaresFromThinBits.pdf)

### Version
0.1.0

### Installation

mkmalwarefrom requires [Python](https://python.org/) and was tested with Python 2.7.13.

```sh
$ git clone https://github.com/SafeBreach-Labs/mkmalwarefrom.git
$ cd mkmalwarefrom
$ python mkmalwarefrom.py -h
```

### Example: Generating /bin/ls from Yahoo

```sh
# assume mkmalwarefrom root directory
$ cat /bin/ls | ./mkmalwarefrom.py -1 http://www.yahoo.com > download_ls.py
$ python download_ls.py > ls2 
$ md5 /bin/ls ls2
```

### Example: Generating /usr/bin/nc from /usr/bin/ssh

```sh
# assume mkmalwarefrom root directory
$ cat /usr/bin/nc | ./mkmalwarefrom.py -2 /usr/bin/ssh > mk_nc.py
$ python mk_nc.py > nc2
$ md5 /usr/bin/nc nc2
```

License
----

BSD 3-Clause

###
