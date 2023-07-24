---
layout: post
title: Allegro Skill File Access Functions
categories: Allegro Skill
date: 2023-07-22
permalink: allegro-skill-file-access-functions
excerpt: 
---

关联lisp文件处理语法[11 Input Output Functions](https://tiny-yhw.github.io//allegro-skill-lisp-input-output-functions){:target="_blank"}

allegro skill File操作 allegro有些专用的函数可以操作文件，allegro本身支持skill的那些文件操作函数，比如infile，outfile函数，而如下的函数 都只是更多的文件操作函数：

### axlOSFileMove 移动文件

```
unless (axlOSFileMove("/mydir/myfile" "/newdir/newfile")
    axlUIConfirm("file move FAILED") 
```

```
(axlOSFileMove "NC.rou" strcat("OUTPUT/" "NC.rou"))
```

### axlOSFileCopy 复制文件

```
unless(axlOSFileCopy("~/myfile" "~/newfile" nil)
    axlUIConfirm("file copy FAILED") )
```

```
file = "nc_param.txt"
        (if (isFile(file) == t) then
                (axlOSFileCopy file strcat("./OUTPUT/" file) nil)    
        )
```

axlDMFileError  
axlDMFindFile  
axlDMGetFile  
axlDMOpenFile  
axlDMOpenLog  
axlDMClose  
axlDMBrowsePath  
axlDMDirectoryBrowse  
axlDMFileBrowse  
axlDMFileParts  
axlOSSlash  
axlRecursiveDelete  
axlTempDirectory  
axlTempFile  
axlTempFileRemove