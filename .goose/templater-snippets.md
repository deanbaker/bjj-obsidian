# Templater Code Snippets

## Date Insertion
```javascript
<% tp.date.now("YYYY-MM-DD") %>
```

## File Rename
```javascript
<%*
const fileName = tp.date.now("YYYY-MM-DD") + "-training";
await tp.file.rename(fileName);
_%>
```

## Class Type Selection
```javascript
<%*
const classTypes = [
    "Gi - Fundamentals",
    "Gi - Advanced",
    "No Gi - Fundamentals",
    "No Gi - Advanced",
    "Open Mat",
    "Private"
];
const selectedType = await tp.system.suggester(classTypes, classTypes);
_%>
```

## Review Date Update
```javascript
<%*
const today = tp.date.now("YYYY-MM-DD");
const file = app.workspace.getActiveFile();
if (file) {
    const currentContent = await app.vault.read(file);
    let updatedContent = currentContent.replace(/last_reviewed: .*/, `last_reviewed: ${today}`);
    await app.vault.modify(file, updatedContent);
}
_%>
```

## Add Partner Roll Details
```javascript
<%*
const partnerName = await tp.system.prompt("Enter training partner's name");
if (partnerName) {
    tR += `\n#### Roll with #${partnerName}\n`
    tR += `- Duration:\n`
    tR += `- Position Control:\n`
    tR += `- Submission Attempts:\n`
    tR += `- What Worked:\n`
    tR += `- What Didn't Work:\n`
    tR += `- Notes for Next Time:\n`
}
_%>
```

## Usage Notes
1. Copy snippets into your templates
2. Adjust variables as needed
3. Test in a new note first
4. Remember to use proper Templater syntax