To install Nmap by compiling it from source code, follow these steps carefully: ( FOR LINUX )

1. Install Required Packages
First, install the necessary packages for compiling Nmap:

 - sudo apt update
 - sudo apt install build-essential libssl-dev

2. Download the Latest Nmap Source Code
Navigate to the official Nmap website, or use wget to download the latest tarball directly. Ensure you replace [version] with the actual version number you are downloading.

 - wget https://nmap.org/dist/nmap-7.95.tar.bz2

3. Extract the Tarball
Extract the downloaded tarball using the tar command:

 - tar jxvf nmap-7.95.tar.bz2

4. Move to the Extracted Directory
Change your directory to the extracted Nmap source code directory:

 - cd nmap-7.95
5. Compile and Install Nmap
Run the following commands to configure, compile, and install Nmap:

 - ./configure
 - make
 - sudo make install


Summary: 
Install Dependencies: Ensures you have the necessary build tools and libraries.
Download Source Code: Gets the latest Nmap source code.
Extract Tarball: Prepares the source code for compilation.
Compile and Install: Configures and builds the source code, then installs Nmap.
Following these steps will compile and install Nmap from the source on your Ubuntu system, giving you access to the latest features and updates.


######################## Below is how we remove nmap from our OS ##############################

 - cd /usr/local
 - rm -f bin/nmap bin/nmapf bin/xnmap
 - rm -f man/man1/nmap.1 man/man1/zenman.1
 - ./bin/uninstall_zenmap

 {You may have to adjust the above commands slightly if you specified --prefix or other install-path option when first installing Nmap. The files relating to zenmap, nmapfe, and xnmap do not exist if you did not install the Zenmap frontend.}