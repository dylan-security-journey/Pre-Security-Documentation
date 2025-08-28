# Windows Security & System Management

---

## 1. BitLocker Drive Encryption
- Available on **Windows 11 Pro** (not on Home edition).  
- Encrypts the drive → protects data if the device is stolen.  

---

## 2. Desktop & File System
- Desktop interface → change icon size, create folders/documents.  
- **NTFS (New Technology File System)**  
  - Journaling file system.  
  - Supports files > 4GB.  
  - Specific permissions, compression, encryption.  
- Permissions → set file access (read-only, modify, etc.).  

<img src="https://github.com/user-attachments/assets/7304191e-f980-4244-9557-c6dd382fbeff" width="600" />

- **Alternate Data Streams (ADS):** Multiple data streams in one file.  
- **System32:** Contains crucial OS files → modifying can break system.  
- System variable for Windows folder: `%windir%`.

---

## 3. User Accounts
- Two types:  
  - **Standard User**  
  - **Administrator**  
- Check users/groups: `lusrmgr.msc`  

<img src="https://github.com/user-attachments/assets/cf85a2a6-10e8-462a-a39c-3d114f92a1d0" width="600" />

- **User Account Control (UAC):**  
  - Prevents privilege abuse by standard users.  
  - Prompts admin approval for sensitive actions (shield icon).  

<img src="https://github.com/user-attachments/assets/0f419a5e-405a-4e25-af18-ffcf99b9ae8d" width="100" />

---

## 4. Control & Monitoring Tools
- **Control Panel / Settings** → System configuration.  
- **Task Manager** → Monitor RAM, CPU, processes.  
- Troubleshooting command:  
  ```cmd
  C:\Windows\System32\control.exe /name Microsoft.Troubleshooting







































