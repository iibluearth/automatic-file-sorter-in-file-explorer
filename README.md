# 📂 Automatic File Sorter in File Explorer

## 📘 Project Overview
This project is a simple Python automation script that organizes files in a given directory (File Explorer) by moving them into categorized folders based on their file extensions. It reduces clutter and keeps documents, images, and text files neatly sorted.

---

## 🚀 Features

- Automatically creates folders for each file type (`csv files`, `image files`, `text files`).
- Moves files into their respective folders (`.csv`, `.png`, `.txt`).
- Prevents overwriting by checking if the file already exists in the destination.
- Works with **any directory** path you specify.

---

## 🛠️ Technologies Used

- **Python**
- **os** (for directory and file path operations)
- **shutil** (for moving files)

---

## 📂 Project Structure

Example before running the script:

```
Python Tutorials/
│── Bike sales dashboard.png
│── FakeFile.txt
│── Project Architecture.png
│── XLOOPUP Excel Tutorial File.xlsx
```

After running the script:

```
Python Tutorials/
│── csv files/
│   └── XLOOPUP Excel Tutorial File.csv
│
│── image files/
│   └── Bike sales dashboard.png
│   └── Project Architecture.png
│
│── text files/
│   └── FakeFile.txt
```

---

## 📝 How It Works

**1.** Define the target path where your files are stored.

**2.** Create subfolders if they don’t already exist.

**3.** Loop through all files in the directory.

**4.** Move files to their appropriate folder based on their extension.

---

## 💻 Code Example

```
import os, shutil 

# Set the directory path
path = r"C:/Users/name/OneDrive/Documents/Python Tutorials/"

# Create folders if they don't exist
folder_names = ['csv files', 'image files', 'text files']
for folder in folder_names:
    if not os.path.exists(path + folder):
        os.makedirs(path + folder)

# List all files in the directory
file_name = os.listdir(path)

# Move files into respective folders
for file in file_name:
    if ".csv" in file and not os.path.exists(path + "csv files/" + file):
        shutil.move(path + file, path + "csv files/" + file)

    elif ".png" in file and not os.path.exists(path + "image files/" + file):
        shutil.move(path + file, path + "image files/" + file)

    elif ".txt" in file and not os.path.exists(path + "text files/" + file):
        shutil.move(path + file, path + "text files/" + file)
```

---

## ⚡ How to Run

**1.** Copy the script into a .py file (example: file_sorter.py).

**2.** Update the path variable with the directory you want to organize.

**3.** Run the script:

```
python file_sorter.py
```

**4.** Check your folder — your files are now neatly organized!
