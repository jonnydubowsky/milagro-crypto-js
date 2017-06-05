# AMCL - *Apache Milagro Crypto JavaScript Library*

* **category**:    Library
* **copyright**:   2016 MIRACL UK LTD
* **license**:     ASL 2.0 - http://www.apache.org/licenses/LICENSE-2.0
* **link**:        https://github.com/miracl/milagro-crypto-js
* **introduction**: [AMCL.pdf](doc/AMCL.pdf)

## Description

*AMCJL - Apache Milagro Crypto JavaScript Library*

AMCJL is a standards compliant JavaScript cryptographic library with no external dependencies, specifically designed to support the Internet of Things (IoT).

For a detailed explanation about this library please read: [doc/AMCL.pdf](doc/AMCL.pdf)

AMCJL is provided in *JavaScript* language

NOTE: This product includes software developed at *[The Apache Software Foundation](http://www.apache.org/)*.

## Requirement for building and testing

[Nodejs](https://nodejs.org/en/) and [npm](https://www.npmjs.com/) are required in order to properly build the library and run tests. Install also the following node.js modules (root permissions may be required)
```
npm install -g jake jake-utils
npm install fs colors assert crypto
```

## Build

The library can be build using [jake](https://www.npmjs.com/package/jake). Type

```
jake -T
```
to see all the options. In order to build the library with the default pairing friendly elliptic curve `BN254CX` and with the support for `RSA2048` type
```
jake build
```
To build supporting other curves or other RSA options you an use the command ```jake build:choice[...]```. For example to build the library supporting the curves `BN254CX` and `C25519` with `RSA4096` type
```
jake build:choice[BN254CX,C25519,RSA4096]
```
To see te list of all the build option type
``` 
jake list
```


## Run tests

```bash
$ git clone https://github.com/miracl/milagro-crypto-js
$ cd tests
$ ./run_test.sh
```
## Information

AMCJL is very simple to build for JavaScript.

First - decide the modulus type and curve type you want to use. Edit ROM.js 
where indicated. You might want to use one of the curves whose details are
already in there.

Three example API files are provided, MPIN.js which 
supports our M-Pin (tm) protocol, ECDH.js which supports elliptic 
curve key exchange, digital signature and public key crypto, and RSA.js
which supports RSA encryption. The first  can be tested using the 
TestMPIN.html driver programs, the second can be tested using TestECDH.html, 
and the third using TestRSA.html

In the ROM.js file you must provide the curve constants. Several examples
are provided there, if you are willing to use one of these.

For quick jumpstart:-

Run Chrome browser and navigate to TestECDH.html

or TestMPIN.html

or BenchtestEC.html

or BenchtestPAIR.html

You might need to wait a couple of minutes for the output to appear.
