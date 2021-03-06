
# Mysql-bruteforce

### MySQL multi-threaded brute-forcer.


## Purpose

Brute force a MySQL user using a wordlist file.


## OS

+ Linux


## Usage

    ./mysql -h <host> -u <username> -f <wordlist_file> [-t <num_threads>] [-p <port>] [-v]


*host* can be localhost (fastest), a hostname, or an IP address.

There are many wordlists available e.g. [Daniel Miessler's](https://github.com/danielmiessler/SecLists/tree/master/Passwords).

`MAX_WORD_LEN` of `50` is fine for most wordlists. However, some wordlists have borked entries (e.g. long email address). For these wordlists, increase `MAX_WORD_LEN` to `140` (or, more precisely, output of `wc -L <wordlist>` + 1), and re-compile to avoid a buffer overrun / segfault.

20 threads appears to be optimal on 4-thread CPUs.

`-v` and `-vv` can be used for verbose output.


## Remote MySQL Connections

See [MySQL-Brute docs](https://github.com/Tinram/MySQL-Brute/blob/master/README.md).


## Build

        make

(See [MySQL-Brute docs](https://github.com/Tinram/MySQL-Brute/blob/master/README.md) for *libmysql* requirements.)


## Authors

+ 0x0mar (original)

+ Tinram (v. 0.02)


## Credits

+ Tim Čas: EOL removal.
+ Ben Alpert: microsecond timer.
