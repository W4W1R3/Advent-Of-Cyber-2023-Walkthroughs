# Day 5
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/8bdb8a7c-f3dd-4c66-9686-597f9b727428)

## Description

Reverse Engineering [ A Christmas DOScovery: Tapes of Yule-tide Past ] — The backup tapes are corrupted. 
They can only be restored using a special program, which can only run in MS-DOS. Explore AntarctiCrafts’ legacy systems and restore the files!

## Day 5 Tasks:

### 1. How large (in bytes) is the AC2023.BAK file?

#### Task 1: File Size Inquiry

      1. Open the DOS application.
      2. Type the command `dir` to view file information.
   
**Answer: 12,704**

### Task 2: Backup Program Name

      1. Navigate to `/TOOLS/BACKUP/`.
      2. Type `edit README.TXT` to access the file.
      3. Read the file content to identify the backup program name.

**Answer: BackupMaster3000**

### Task 3: Backup File Signature

      To ensure proper backup restoration, check the correct bytes in the backup's file signature.

**Answer: 41 43**

### Task 4: Flag Retrieval after Backup Restoration

      1. Type `edit AC2023.BAK` to open the file.
      2. Change the specified values to `41 43`, press Alt+F, and save.
      3. Execute `C:\TOOLS\BACKUP\BUMASTER.EXE AC2023.BAK`.

**Flag: THM{0LD_5CH00L_C00L_d00D}**
