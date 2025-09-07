# Python Project 11: File Organizer Script 🗂️⚙️

## 📌 Problem Statement:  
Create a Python script that automatically organizes files in a folder by file type — putting images, docs, videos, etc., into separate subfolders.

##  🧠 What You'll Learn:

- File system navigation (using os)  
- Moving files with shutil  
- Handling file extensions  
- Automating daily productivity tasks

##  ✅ Python Code:
```
import os
import shutil

def organize_folder(folder_path):
    file_types = {
        'Images': ['.jpg', '.jpeg', '.png', '.gif'],
        'Documents': ['.pdf', '.docx', '.txt', '.xlsx'],
        'Videos': ['.mp4', '.avi', '.mkv'],
        'Audio': ['.mp3', '.wav'],
        'Archives': ['.zip', '.rar'],
        'Scripts': ['.py', '.js']
    }

    for filename in os.listdir(folder_path):
        file_path = os.path.join(folder_path, filename)
        if os.path.isfile(file_path):
            _, ext = os.path.splitext(filename)
            for folder, extensions in file_types.items():
                if ext.lower() in extensions:
                    target_folder = os.path.join(folder_path, folder)
                    os.makedirs(target_folder, exist_ok=True)
                    shutil.move(file_path, os.path.join(target_folder, filename))
break

#Example usage
organize_folder("/path/to/your/folder")
```

## 📤 What It Does:

1. Scans your folder for files  
2. Checks each file’s extension  
3. Moves them to a matching subfolder (auto-created)

## 🔧 Try Modifying:

- Add logging for moved files  
- Schedule it with Task Scheduler / Cron  
- Add GUI with Tkinter

## 💡 Use Cases:

✅ Clean up messy downloads folder  
✅ Auto-sort project folders  
✅ Boost productivity in seconds  
