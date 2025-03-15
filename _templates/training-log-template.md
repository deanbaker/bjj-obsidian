<%*
const fileName = tp.date.now("YYYY-MM-DD") + "-training";
await tp.file.rename(fileName);

// Class type selection
const classTypes = ["Advanced", "All Ranks", "Open Mat", "Social"];
const selectedType = await tp.system.suggester(classTypes, classTypes);
_%>
---
type: training
date: <% tp.date.now("YYYY-MM-DD") %>
class_type: <% selectedType %>
instructor: 
energy_level: 
tags: [training]
---

# Training Log - <% tp.date.now("YYYY-MM-DD") %>

## Class Focus
- 

## Techniques Covered
1. 
2. 
3. 

## Rolling Notes
### What Worked Well
- 

### Areas for Improvement
- 

### New Problems to Solve
- 

### Rolling Partners
```button
name ➕ Add Rolling Partner
type command
action Templater: Open insert template modal
```

## Key Takeaways
- 

## Follow-up Items
- [ ] 
- [ ] 

## Recovery Notes
- Physical state:
- Areas of soreness:
- Recovery plans: