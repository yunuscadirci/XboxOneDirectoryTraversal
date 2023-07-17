XBox One Directory Traversal and Information Exposure
Note from 2023
This vulenrability found late 2019 while working some protocol vulnerabilities like CallStranger on my old XBox one. After sending early report to Microsoft, Files application removed from XBox One https://www.reddit.com/r/xboxone/comments/ebrrf1/working_alternatives_to_xbox_file_explorer/ https://twitter.com/xboxinsider/status/1202357755140546560 and report is not accepted tagging 'nonproducable' . I stopped researching for other attacks 

Xbox One OS Version 10.0.18363.8119 (19h1_release_xbox_dev_1911.191119-1135) has Directory Traversal and Information Leakage vulnerabilities
Directory Traversal (CWE-22 Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal') )

When we open File Explorer application on Xbox One, we see 8 empty folders :
![image001](https://github.com/yunuscadirci/XboxDirectoryTraversal/assets/7267858/8b5fb44c-110d-4c2e-a103-9a1c99d33bdb) 

As soon as we  write .. in Search area in File Explorer applications, we can access some folders   we didn’t see before
 ![image003](https://github.com/yunuscadirci/XboxDirectoryTraversal/assets/7267858/95cb0cc8-106a-4811-9e95-d5cb6689ab62)

We can browse into these folders:
  ![image005](https://github.com/yunuscadirci/XboxDirectoryTraversal/assets/7267858/f3b4fedb-b83f-46c2-8fe0-535f9f341b3c)



Information Exposure (CWE-200  Information Exposure )
We can copy this Edge backup folders to external USB drive and analyze on computer. They are standart edb files and some log files.
![image009](https://github.com/yunuscadirci/XboxDirectoryTraversal/assets/7267858/d3a6db1e-4a4a-4daf-af2c-448a86401612)

EDB Files

We can analyze EDB files with ESEDatabaseView  https://www.nirsoft.net/utils/ese_database_view.html application easily. 
 ![image011](https://github.com/yunuscadirci/XboxDirectoryTraversal/assets/7267858/a52f07b0-1812-4542-8db1-4f2bec0c5d24)

Log Files
When we analyzed .log files, we saw internal directory structure of Edge for Xbox One 
 
