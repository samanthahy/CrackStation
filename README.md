# Project Title

CrackStation


## Description

This project uses a swift package to realize the function of decrypting the plaintext password behind an input SHA1 hash. Target code checks availability of the input hash in a lookup table that is added as resources in the package, then returns its plaintext password if found there or return nil if the hash is not in our data. Test target code contains tests that check if the resource json file is generated and loaded well, if the input is cracked correctly, etc. An abstract programming interface(API) named Decrypter is placed in the main target to conform with our CrackStation. 

## Getting Started

### Dependencies

* Swift
* IDE
    * Mac: Xcode
    * Windows 10: Docker desktop(https://docs.docker.com/desktop/install/windows-install/)<br />
                  Visual Studio Code(https://code.visualstudio.com/Download)
* Terminal
    * Git Bash/ PowerShell/ Cmd

### Executing program

* Clone the program<br />
In terminal, create a directory on you local machine. Change to the directory, clone our repository to your directory.
```
mkdir your-dictionary
cd your-dictionary
git clone git@github.com:nic252525/CrackStation.git
```

* Generate a lookup table<br />
Two ways to generate a lookup table. The first is to run hashGenerator.py in Sources/CrackStation to generate a data.json in the same directory.
The second is to call CrackStation().JsonSaver() to generate a data.json in your user Directory, then manually copy it to the Sources/CrackStation. Don't recommend using it.

* Build and test the package<br />
Change to CrackStation directory, run test command to build and test the swift package.
```
swift test
```

## Authors

Yun Han 
[hanyun@oregonstate.edu]

## Version History

* 2.0.0
    * Updates for POC v2: crack any password up to two characters in length, which (a) matches the regular expression[A-Za-z0-9]{1,2} and (b) is encrypted using SHA-1.
    * Switch to branch POCv2 to check the code.

* 1.0.0
    * Release for POC v1: crack crack any single-character password, which (a) matches the regular expression [A-Za-z0-9] and (b) is encrypted using SHA-1.
    * Default to be on the main branch.

* 0.1.1
    * Initial Release