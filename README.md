# Detecting-steganography-with-tools-like-StegExpose-analyzing-file-signatures
## AIM:
To detect hidden data using steganography detection tools like StegExpose and analyze file signatures for authenticity and manipulation.
## Requirements:
- **Operating System:** Linux / Windows
- **Tools:**
    - StegExpose (Java-based tool)
    - Hex Editor (e.g., xxd, HxD)
    - File command (Linux) or TrID (Windows)
- **Sample files:**
    - Suspected stego files (.jpg, .png, .wav)
    - Clean reference files
## ARCHITECTURE DIAGRAM:
```mermaid
flowchart TD
    A[Input File: JPG/PNG/WAV] --> B[File Signature Analysis]
    B --> C{Signature Match?}
    C -- Yes --> D[Pass to StegExpose]
    C -- No --> E[File Tampered / Mismatch]
    D --> F[StegExpose Detection: Suspicious or Clean]
    F --> G[Report Findings]
```

## DESIGN STEPS:
### Step 1:
Install StegExpose or use the JAR version to detect steganography in image files.

### Step 2:
Run StegExpose on a directory of suspected image files using the command:

### Step 3:
Analyze file signatures using tools like file, binwalk, or xxd to check for inconsistencies or embedded content.

## PROGRAM:
**Check file type**
```bash
file image.jpg
```
or view magic bytes:
```
xxd image.jpg | head
```

<img width="728" height="283" alt="image" src="https://github.com/user-attachments/assets/6d783ef7-aa23-4b1e-b613-51ac70165661" />

**Run StegExpose**
```bash
java -jar StegExpose.jar suspect.jpg
```
instead of StegExpose an alternative tool binwalk is used
```
binwalk wallpaper.jpg
```
<img width="735" height="126" alt="image" src="https://github.com/user-attachments/assets/8a55eeda-51db-42cc-bb55-0474f2ae055f" />

## OUTPUT:
List of Images with Steganography Detection Scores and File Signature Details
<img width="1127" height="535" alt="image" src="https://github.com/user-attachments/assets/f664b97d-2cfb-4483-895d-39adcc99e776" />

## RESULT:
Hidden data was successfully detected and file signatures were analyzed for irregularities.
