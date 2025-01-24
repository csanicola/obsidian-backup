# Index
## 01 - Rough Notes
```dataview 
TABLE file.mday as "Last Modified"
FROM "01 - Rough Notes"
SORT file.mday asc
```
---
## 02 - Source Material

This section is for collecting external references, with subcategories for organizing different types of sources.

### Articles
Links to or pdf/docs of relevant articles.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/Articles"
sort file.mday asc
```

### Books
Book summaries, notes, or links to books I’m reading.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/Books"
sort file.mday asc
```

### GitHub Repos
Key GitHub repositories or projects you’re following.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/GitHub Repos"
sort file.mday asc
```

### Helpful Websites and Apps
Websites, tools, or apps useful for research or work.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/Helpful Websites and Apps"
sort file.mday asc
```

### Other
Any additional references.
```dataview 
TABLE file.mday  as "Last Modified"
FROM "02 - Source Material/Other"
sort file.mday asc
```

### Papers
Academic or research papers with summaries and highlights.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/Papers"
sort file.mday asc
```

### Videos
Useful videos with links or embedded content.
```dataview 
TABLE file.mday as "Last Modified"
FROM "02 - Source Material/Videos"
sort file.mday asc
```

---
## 03 - Tags

Organize your content with tags for easy searching and grouping. Use these for projects, topics, or themes.

- **Tags by Topic**
    - e.g., #statistics, #machine_learning, #healthcare
- **Tags by Priority**
    - e.g., #urgent, #followup

```dataview 
TABLE file.mday as "Last Modified"
FROM "03 - Tags"
sort file.mday asc
```
---
## 04 - Indexes

Use this section to create an overview of your vault's most important files, categorized or alphabetized.

- **Project Index**
    - An index of all ongoing projects, with links to individual files.
- **Topic Index**
    - e.g., #BariatricSurgery, #DataAnalysis
- **Paper Index**
    - A list of all research papers, summaries, and annotations.
```dataview 
TABLE file.mday as "Last Modified"
FROM "04 - Indexes"
sort file.mday asc
```
---
## 05 - Templates

This section is for storing templates for frequently used formats. You can create templates for daily notes, project outlines, meeting minutes, etc.
```dataview 
TABLE file.mday as "Last Modified"
FROM "05 - Template"
sort file.mday asc
```

CSS Note Background Options:
- `page-manila` - background is cream colored with a black pen
- `page-white` - background is white with a black pen
- `page-blueprint` - background is blue with the pen white
- `page-grid` - makes the background a grid layout
- `pen-white`
- `pen-blue`
- `pen-red`
- `pen-green`
- `pen-black`
- `pen-gray`
- `pen-purple`

---
## 06 - Main Notes

This is my core working area for structured content like training, projects, and daily notes.

### 01 - Training Courses  
Tracking the online courses I’m taking and my progress.
    - Course Name
    - Key Learnings
    - Assignments/Quizzes
```dataview 
TABLE file.mday as "Last Modified"
FROM "06 - Main Notes/01 - Training Courses"
sort file.mday asc
```

### 02 - Projects  
Dedicated space for your current projects, with links to files and task lists.
    - Project 1
    - Project 2
```dataview 
TABLE file.mday as "Last Modified"
FROM "06 - Main Notes/02 - Projects"
sort file.mday asc
```

### 03 - Daily Note  
Keep a running log of daily tasks, meetings, or reflections.
*-Won’t be including a full file list of these-*

### 04 - Data Science 
Place to keep all notes related to data science
```dataview 
TABLE file.mday as "Last Modified"
FROM "06 - Main Notes/04 - Data Science"
sort file.mday asc
```

### 05 - Meetings 
A place to keep all notes from meetings
```dataview 
TABLE file.mday as "Last Modified"
FROM "06 - Main Notes/05 - Meetings"
sort file.mday asc
```


___
## 07 - Personal
Personal notes and documents
```dataview 
table file.mday as "Last Modified"
from "07 - Personal"
where file.folder != "07 - Personal/00 - Safety Box"
and file.folder != "07 - Personal/01 - Learn"
and file.folder != "07 - Personal/02 - Books"
and file.folder != "07 - Personal/02 - Books/01 - Personal Books"
sort file.mday desc
```
### 00 - Safety Box
Where all the important documents are:
```dataview 
table file.mday as "Last Modified"  
FROM "07 - Personal/00 - Safety Box"
sort file.mday asc
```

### 01 - Learn
Where personal learning takes place
```dataview 
TABLE file.mday as "Last Modified"
FROM "07 - Personal/01 - Learn"
sort file.mday asc
```

### 02 - Books 
```dataview 
TABLE file.mday as "Last Modified"
FROM "07 - Personal/02 - Books"
sort file.mday asc
```
### 03 - Media 
```dataview 
TABLE file.mday as "Last Modified"
FROM "07 - Personal/03 - Media"
sort file.mday asc
```


___
## 08 - Research
Stony Brook University Research Documents and Tracking 
```dataview 
table file.mday as "Last Modified"
from "08 - Research"
where file.folder != "08 - Research/Archived Studies"
and file.folder != "08 - Research/Current Studies"
sort file.mday desc
```
### Archived Studies
```dataview 
TABLE file.mday as "Last Modified"
FROM "08 - Research/Archived Studies"
sort file.mday asc
```

### Current Studies
```dataview 
TABLE file.mday as "Last Modified"
FROM "08 - Research/Current Studies"
sort file.mday asc
```

## 09 - Clippings 
A place for all the web clippings imported directly from the chrome extension
```dataview 
TABLE file.mday as "Last Modified"
FROM "09 - Clippings"
sort file.mday asc
```

---
## 99 - Archived

Store old or completed projects, notes, and tasks here to keep your workspace clean without losing information.

### Archived Projects
Completed or paused projects.
### Archived Notes
Notes that are no longer active but might be useful later.
