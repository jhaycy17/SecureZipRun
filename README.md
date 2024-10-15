# ZipGate
A gateway controlled by HWID for zip file extraction and executable running

Description:
This Python-based application is designed for secure file extraction and execution, featuring hardware-based authentication (HWID) and secure zip file handling. The program ensures that only authorized systems can extract and execute sensitive files by leveraging HWID authentication and password-protected zip archives. Key security features include:

HWID-Based Authentication:

The program authenticates the user's system using a unique hardware ID (HWID).
On the first run, it connects to a remote Pastebin URL that contains a whitelist of approved HWIDs.
If the HWID is valid, it stores an encrypted version locally for offline use, allowing subsequent runs without needing to reauthenticate.
This ensures that only authorized systems can run the executable and access the extracted files.
Password-Protected Zip File Extraction:

The application extracts files from a password-protected zip archive located on the user's system (e.g., Desktop).
The extraction only occurs after successful HWID authentication, ensuring that unauthorized users cannot access the files.
Execution and Cleanup:

After extracting the zip file, the program automatically runs an executable file within the zip.
After execution, the program securely deletes specified files, preventing recovery from the recycle bin by performing a permanent file deletion.
Encryption:

The HWID is encrypted using the cryptography library (Fernet symmetric encryption) before being stored locally.
This provides an additional layer of security, protecting the HWID from tampering or unauthorized access.
Threading:

The script runs the executable in a separate thread, allowing it to monitor the process and delete the files promptly after execution.
Key Features:
HWID Authentication: Verifies the user's system against a whitelist of HWIDs.
Password-Protected Zip Extraction: Only authorized users can extract sensitive files from the zip.
Permanent File Deletion: Ensures that extracted files are securely deleted after execution.
Offline Authentication: After the first run, the program no longer requires an internet connection for HWID verification.
Encryption: Protects the stored HWID using Fernet encryption.
Use Cases:
Protect sensitive files and executables from unauthorized access.
Ensure that distributed software can only be run on approved machines.
Automate secure extraction, execution, and cleanup of files.
