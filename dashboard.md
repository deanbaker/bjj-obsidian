# BJJ Training Dashboard 🥋

## Quick Create 📝

### Training Notes
```button
name 📝 New Training Log
type command
action Templater: Create new note from template
```

### Position Study
```button
name 🔍 New Position Note
type command
action Templater: Create new note from template
```

### Techniques
```button
name 🥋 New Technique Note
type command
action Templater: Create new note from template
```

### Competition
```button
name 🏆 New Competition Note
type command
action Templater: Create new note from template
```

### Resources
```button
name 📚 New Resource Page
type command
action Templater: Create new note from template
```

## Recent Notes 📅
```dataview
TABLE file.ctime as Created
FROM "training-logs"
SORT file.ctime DESC
LIMIT 5
```

## Recent Competition Notes 🏆
```dataview
TABLE file.ctime as Created
FROM "competition"
SORT file.ctime DESC
LIMIT 3
```

## Navigation 🗺️
- [[main-positions|Position Map]]
- [[half-guard-system|Half Guard System]]
- [[half-guard-sweeps-study|Sweep Study Guide]]

## Quick Stats 📊
```dataview
TABLE length(file.outlinks) as "Links"
FROM "positions" or "techniques"
SORT length(file.outlinks) DESC
LIMIT 5
```

## Tags Overview 🏷️
```dataview
TABLE length(rows) as "Count"
FROM #position or #technique or #training
GROUP BY file.tags as Tag
SORT length(rows) DESC
```