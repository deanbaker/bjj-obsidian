<%*
const today = tp.date.now("YYYY-MM-DD");
const reviewEntry = `- Reviewed: ${today}`;

// Get the active file's content
const file = app.workspace.getActiveFile();
if (file) {
    // Read the current content
    const currentContent = await app.vault.read(file);
    
    // Update frontmatter last_reviewed date
    let updatedContent = currentContent.replace(/last_reviewed: .*/, `last_reviewed: ${today}`);
    
    // Add to review history
    const historySection = "### Review History";
    const historyIndex = updatedContent.indexOf(historySection);
    if (historyIndex !== -1) {
        // Insert after the Review History heading
        updatedContent = updatedContent.slice(0, historyIndex + historySection.length) + 
                        "\n" + reviewEntry + 
                        updatedContent.slice(historyIndex + historySection.length);
    }
    
    // Write back to file
    await app.vault.modify(file, updatedContent);
    
    // Confirmation message
    new Notice(`Review date updated to ${today}`);
}
_%>