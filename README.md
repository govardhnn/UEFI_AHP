# UEFI_AHP

My Additional Hands-On Project for the Subject 'Embedded Firmware Developement using UEFI' included performing the tianocore's edkII installation, setup and demonstration on Quick EMUlator (QEMU) 

The following is a script to get started on edkII using QEMU

cd to a workspace
`git clone https://github.com/tianocore/edk2.git`
`cd edk2`
`git submodule update --init`
`cd ..`

Edit the config file (target.txt)

Install dependencies

python at C:\Program Files\Python38
ASL, NASM into C:\
Python 27
Visual Studio 2019

Open VS2019 Shell
![image](https://user-images.githubusercontent.com/37037342/232229042-c20df4bc-8c6f-4b80-ae15-fbe85f01c819.png)

`cd C:\Users\saigo\Desktop\tianocore\toolchain\edk2`
`set PYTHON_HOME=C:\Python27\`
`set NASM_PREFIX=C:\NASM\`
`edksetup.bat`
`build -t VS2019`

![image](https://user-images.githubusercontent.com/37037342/232229097-aa1a6860-9137-4915-9ed8-e6445cce6570.png)

Locate QEMU in Program files, open in CMD, and enter the following command

`qemu-system-x86_64 
-cpu qemu64  
-drive  if=pflash,format=raw,unit=0,file=C:\Users\saigo\Desktop\tianocore\toolchain\edk2\Build\OvmfX64\DEBUG_VS2019\FV\OVMF_CODE.fd,readonly=on 
-drive if=pflash,format=raw,unit=1,file=C:\Users\saigo\Desktop\tianocore\toolchain\edk2\Build\OvmfX64\DEBUG_VS2019\FV\OVMF_VARS.fd 
-net none`

![image](https://user-images.githubusercontent.com/37037342/232229130-20962cc0-b272-4364-b8dd-76f36ab0269b.png)
![image](https://user-images.githubusercontent.com/37037342/232229164-4d6cde9b-7bc5-430a-94f0-2824bdee6b5d.png)
![image](https://user-images.githubusercontent.com/37037342/232229168-1a80a5b7-29e9-4b3b-9464-31f86aec5a91.png)
![image](https://user-images.githubusercontent.com/37037342/232229170-73d04348-0286-4d43-b916-9b4715ae9f96.png)
![image](https://user-images.githubusercontent.com/37037342/232229178-189235d9-eb58-4433-8a74-da9259a3ea12.png)

All the reference commands can be found listed in the UEFI Shell Specification: https://uefi.org/sites/default/files/resources/UEFI_Shell_2_2.pdf \
Note: Chapter 5 is a good collation of all the commands
![image](https://user-images.githubusercontent.com/37037342/232229221-bd8c4b81-6d8f-4a66-98d9-cee7bb8c22b1.png)

