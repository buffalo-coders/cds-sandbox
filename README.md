# org.buffalo-coders:cds-sandbox

Sandbox area where I am playing around with Java's Class Data Sharing (CDS).

## Usage

Build the project and run the CDS Sandbox test:

```sh
make run
```

```sh
RUNNING CDS SANDBOX TEST

SHARE: OFF
time java -Xshare:off -XX:+UnlockDiagnosticVMOptions -XX:SharedArchiveFile=target/cds-sandbox.jsa -jar target/cds-sandbox*.jar
Hello World!

real    0m0.111s
user    0m0.080s
sys     0m0.029s

SHARE: DUMP
time java -Xshare:dump -XX:+UnlockDiagnosticVMOptions -XX:SharedArchiveFile=target/cds-sandbox.jsa -jar target/cds-sandbox*.jar
Allocated shared space: 37871616 bytes at 0x0000000800000000
Loading classes to share ...
Loading classes to share: done.
Rewriting and linking classes ...
Rewriting and linking classes: done
Number of classes 2203
    instance classes   =  2189
    obj array classes  =     6
    type array classes =     8
Calculating fingerprints ... done.
Removing unshareable information ... done.
Shared Lookup Cache Table Buckets = 8216 bytes
Shared Lookup Cache Table Body = 65952 bytes
ro space:   5693328 [ 35.4% of total] out of  16777216 bytes [33.9% used] at 0x0000000800000000
rw space:   8954128 [ 55.7% of total] out of  16777216 bytes [53.4% used] at 0x0000000801000000
md space:   1403000 [  8.7% of total] out of   4194304 bytes [33.5% used] at 0x0000000802000000
mc space:     34053 [  0.2% of total] out of    122880 bytes [27.7% used] at 0x0000000802400000
total   :  16084509 [100.0% of total] out of  37871616 bytes [42.5% used]

real    0m0.237s
user    0m0.175s
sys     0m0.047s

SHARE: ON
time java -Xshare:on -XX:+UnlockDiagnosticVMOptions -XX:SharedArchiveFile=target/cds-sandbox.jsa -jar target/cds-sandbox*.jar
Hello World!

real    0m0.099s
user    0m0.066s
sys     0m0.032s
```

## Status

[![Build Status](https://travis-ci.com/buffalo-coders/cds-sandbox.svg?branch=master)](https://travis-ci.com/buffalo-coders/cds-sandbox)
