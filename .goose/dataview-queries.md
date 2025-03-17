# Useful Dataview Queries

## Recent Activity
```dataview
TABLE file.ctime as Created
FROM "training-logs"
SORT file.ctime DESC
LIMIT 5
```

## Tag Overview
```dataview
TABLE length(rows) as "Count"
FROM "/"
FLATTEN file.tags AS tag
GROUP BY tag
SORT length(rows) DESC
```

## Position Links
```dataview
TABLE length(file.outlinks) as "Links"
FROM "positions"
SORT length(file.outlinks) DESC
```

## Training Partner Stats
```dataview
TABLE length(rows) as "Rolls"
FROM "training-logs"
FLATTEN file.tags as partner
WHERE contains(partner, "#partner/")
GROUP BY partner
SORT length(rows) DESC
```

## Usage Tips
1. Copy queries directly into your notes
2. Adjust LIMIT values as needed
3. Modify sorting for different views
4. Add WHERE clauses to filter results