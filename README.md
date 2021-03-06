![GitHub issues](https://img.shields.io/github/issues/somdipdey/Encrypted_QR_Code.svg)
![Twitter](https://img.shields.io/twitter/url/https/github.com/somdipdey/Encrypted_QR_Code.svg?style=social)

# Encrypted QR Code (qrcrypto)

Use this package to encrypt messages and embed in QR code, and decode the message back.

#### Build for Linux and OSX:
[![Build Status](https://travis-ci.org/somdipdey/Encrypted_QR_Code.svg?branch=master)](https://travis-ci.org/somdipdey/Encrypted_QR_Code)
[![License: MIT](https://img.shields.io/badge/License-MIT-red.svg)](https://github.com/somdipdey/Encrypted_QR_Code/blob/master/LICENSE)

## Dependencies

	$ [sudo] pip install qrcode
	$ [sudo] pip install simple-crypt
	$ [sudo] pip install pypng
	$ [sudo] pip install zbar
	$ [sudo] pip install pillow

### Note:

If you are using Python3.X and not Python2 then you would receive an error while installing zbar. In that case install pypng and pillow packages and then for zbar follow these steps:

	$ brew install zbar
	$ export LDFLAGS="-L$(brew --prefix zbar)/lib"
	$ export CFLAGS="-I$(brew --prefix zbar)/include"
	$ pip install zbarlight

The aformentioned steps would install zbarlight. For more information consult their webpage: https://github.com/Polyconseil/zbarlight 

## Installation


### Step 1:
	$ git clone https://github.com/somdipdey/Encrypted_QR_Code.git
	$ cd Encrypted_QR_Code
	$ [sudo] python setup.py install

### Step 2:
And then install zbarlight as mentioned before:

	$ brew install zbar
	$ export LDFLAGS="-L$(brew --prefix zbar)/lib"
	$ export CFLAGS="-I$(brew --prefix zbar)/include"
	$ pip install zbarlight

Note:

You can also install the package, mentioned in Step 1, by using pip install as follows:

	$ pip install git+https://github.com/somdipdey/Encrypted_QR_Code.git

And then follow Step 2.

## Usage

### Encryption

To encrypt a meesage and then embed it in the QR code just type the following command in the command prompt:

	$ python encrypt_qr.py {message} {qr_file_name} {password}

For example::

	$ python encrypt_qr.py 'my hobby is everything' hello 'My Secret'

If you use the following command, you will see a QR code with name 'hello.PNG' is generated in the /Output/ folder. Upon inspection, you can see the QR code holds the encrypted message, i.e. 'my hobby is everything'.

#### hello.PNG QR code with embedded encrypted meesage::

<img width="350" alt="hello.PNG QR code with embedded encrypted meesage" src="https://github.com/somdipdey/Encrypted_QR_Code/blob/master/qrcrypto/Output/hello.PNG">

### Decryption

To decrypt the message from the QR code just type the following command in the command prompt:

	$ python decrypt_qr.py {qr_file_name} {password}

For example::

	$ python decrypt_qr.py hello 'My Secret'

	Output::

	>>'my hobby is everything'

## Note:
This package is implemented using Simple-Crypt encryption python package, which uses PBKDF (Key derivation function) to make guessing of password hard hence secruing from brute-force attacks. The use of PBKDF makes the algorithm slow and hence creating an encrypted QR code is slow and decrypting is slow as well. More about simple-crypt package can be accessed here: https://github.com/andrewcooke/simple-crypt

## Help Us To Keep Going
If you really liked our work then do not forget to hit the 'Star' button. Your encouragement towards us will keep us going! 

![GitHub stars](https://img.shields.io/github/stars/somdipdey/Encrypted_QR_Code.svg)
