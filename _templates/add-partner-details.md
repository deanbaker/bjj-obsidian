<%*
// Prompt for partner name
const partnerName = await tp.system.prompt("Enter training partner's name");
if (partnerName) {
    // Create the section
    tR += `\n#### Roll with #${partnerName}\n`
    tR += `- Duration:\n`
    tR += `- Position Control:\n`
    tR += `- Submission Attempts:\n`
    tR += `- What Worked:\n`
    tR += `- What Didn't Work:\n`
    tR += `- Notes for Next Time:\n`
}
_%>