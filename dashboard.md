# BJJ Training Dashboard 🥋

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
FROM "/"
FLATTEN file.tags AS tag
GROUP BY tag
SORT length(rows) DESC
```