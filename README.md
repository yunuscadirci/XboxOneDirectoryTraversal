# XBox One Directory Traversal and Information Exposure
# Xbox One OS Version 10.0.18363.8119 (19h1_release_xbox_dev_1911.191119-1135) has Directory Traversal and Information Leakage vulnerabilities
## Note from 2023
This vulnerability was found late 2019 while working on some protocol vulnerabilities like CallStranger on my old XBox one. I've sent early report to Microsoft and went on a work trip. When I was back I saw File Explorer application was removed from XBox One https://www.reddit.com/r/xboxone/comments/ebrrf1/working_alternatives_to_xbox_file_explorer/ https://twitter.com/xboxinsider/status/1202357755140546560 and report was not accepted with an attached tag 'non-reproducable' . I stopped working on XBox One after this ridiculous reply by MS Security team.




## Directory Traversal (CWE-22 Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal') )

When we open File Explorer application on Xbox One, we see 8 empty folders :
![image001](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/a815128d-0e75-4bad-83a2-031a37ad3e41)


As soon as we  write .. in Search area in File Explorer applications, we can access some folders   we didn’t see before
![image003](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/86a5b690-d712-4ddf-8598-712a9d8c5585)


We can browse into these folders:

![image005](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/57dc7511-f1af-4175-a409-8e2007161f72)
![image007](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/99eadf29-988f-4a20-930e-e30143e90724)



## Information Exposure (CWE-200  Information Exposure )
We can copy this Edge backup folders to external USB drive and analyze on computer. They are standart edb files and some log files.


EDB Files

We can analyze EDB files with ESEDatabaseView  https://www.nirsoft.net/utils/ese_database_view.html application easily. 
![image010](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/a81c06ab-f0dc-46e1-a1f3-20d308487e0f)

Log Files
When we analyzed .log files, we saw internal directory structure of Edge for Xbox One 
 ![image012](https://github.com/yunuscadirci/XboxOneDirectoryTraversal/assets/7267858/8086d1e2-b4ff-46fe-9fdc-aa1f49cabf5c)

