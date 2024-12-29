[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
[[How to use this vault?]]
# TO-DO
*everything I gotta do*
```dataviewjs
const tag = "#tracker/task"
const query = `
not done
${"(path includes " + dv.pagePaths(tag).join(') OR (path includes ') + ")"}
# you can add any number of extra Tasks instructions, for example:
hide start date
hide recurrence rule
hide edit button
hide created date
hide scheduled date
hide tags
sort by due date
`

dv.paragraph('```tasks\n' + query + '\n```');

```
# Period Tracker
<%*
const progress = await tp.system.suggester(
  ["not on period", "started (Period begins today)", "middle (current cycle)", "ended"],
  ["not", "started", "middle", "ended"]
);

// Initialize cycle variable and handle Dataview data
let cycle = 0; // Default to 1 if no valid data exists

try {
  // Access Dataview API and filter valid cycle data
  const notes = app.plugins.plugins.dataview.api.pages('"01_Daily_notes"')
    .filter(p => p.period_cycle !== undefined && !isNaN(Number(p.period_cycle)));

  if (notes.length > 0) {
    // Extract all cycle numbers as numbers
    const cycles = notes.map(p => Number(p.period_cycle));
    const lastCycle = Math.max(...cycles);

    // Increment cycle if progress is "started," otherwise keep it the same
    cycle = (progress === "started") ? lastCycle + 1 : lastCycle;
  }
} catch (error) {
  console.error("Error fetching or processing Dataview data:", error);
}

// Generate template output
if (progress !== "not on period") {
  const flow = await tp.system.suggester(
    ["light (Minimal flow)", "medium (Moderate flow)", "heavy (Strong flow)"],
    ["light", "medium", "heavy"]
  );

  const mood = await tp.system.suggester(
    ["happy (Feeling good)", "neutral (No strong feelings)", "sad (Feeling down)"],
    ["happy", "neutral", "sad"]
  );

  const pain = await tp.system.suggester(
    ["no (No pain)", "mild (Slight discomfort)", "moderate (Manageable pain)", "severe (Intense pain)"],
    ["no", "mild", "moderate", "severe"]
  );

  tR += `- period_cycle:: ${cycle}\n`;
  tR += `- period_progress:: ${progress}\n`;
  tR += `- period_flow:: ${flow}\n`;
  tR += `- mood:: ${mood}\n`;
  tR += `- pain:: ${pain}\n`;
} else {
  tR += `- period_cycle:: ${cycle}\n`;
  tR += `- period_progress:: ${progress}\n`;
}
%>
# Daily Notes
*Notes about my day, where I add TO-DOs*

# Daily Log
*Tracking daily task lengths*

# Dairy
*For when I have something personal to add*
