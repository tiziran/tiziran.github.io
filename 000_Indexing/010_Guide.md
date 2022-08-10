---
updated: 2022-08-10T22:38:55+02:00
created: 2022-08-10T22:32:18+02:00
Tags: index, RandD, tagsin
project: Farshid
why: main index file
site: https://www.tiziran.com 
---
top: [[010_Guide]]

List of all folders 
```dataview
table  
GROUP BY file.folder				
```

---

All index and MOC files 
```dataview
TABLE file.mtime AS "Last Modified", tags
From #index
sort file.name ASC
```


---

