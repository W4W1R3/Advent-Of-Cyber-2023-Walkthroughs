# Day 5
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/8bdb8a7c-f3dd-4c66-9686-597f9b727428)

## Description

Reverse Engineering [ A Christmas DOScovery: Tapes of Yule-tide Past ] — The backup tapes are corrupted. 
They can only be restored using a special program, which can only run in MS-DOS. Explore AntarctiCrafts’ legacy systems and restore the files!

<h1>If you are on Windows, use Remote Desktop Connection else use rdpclient</h1>

## Day 5 Tasks:

### 1. How large (in bytes) is the AC2023.BAK file?

#### Task 1: File Size Inquiry

      1. Open the DOS application.
      2. Type the command `dir` to view file information.

      ![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/e6fac3d0-818d-4251-a08d-0de873aa2c0a)

   
**Answer: 12,704**

### Task 2: Backup Program Name

      1. Navigate to `/TOOLS/BACKUP/`.
      2. Type `edit README.TXT` to access the file.
      3. Read the file content to identify the backup program name.

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/75c9c193-3175-4f3b-be50-089f21178e09)


**Answer: BackupMaster3000**

### Task 3: Backup File Signature

      To ensure proper backup restoration, check the correct bytes in the backup's file signature.

      ![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/a8f5f78d-0bca-4ceb-b34e-fbd2ae1e7c61)


**Answer: 41 43**

### Task 4: Flag Retrieval after Backup Restoration

      1. Type `edit AC2023.BAK` to open the file.
      2. Change the specified values to `41 43`, press Alt+F, and save.

As we can see, the current bytes are set to XX. According to the troubleshooting section we've read, BUMASTER.EXE expects the magic bytes of a file to be 41 43. 
These are hexadecimal values, however, so we need to convert them to their ASCII representations first.

You can convert these manually using an ASCII table or online converters

Go back to the MS-DOS Editor window, move your cursor to the first two characters, remove XX, and replace it with AC. Once that's done, save the file by going to "File > Save".

      3. Execute `C:\TOOLS\BACKUP\BUMASTER.EXE AC2023.BAK`.

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/4910f68a-d84b-4ec9-ac1e-bda3f599e41c)

**Flag: THM{0LD_5CH00L_C00L_d00D}**
