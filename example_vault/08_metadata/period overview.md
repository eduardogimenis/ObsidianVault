
```dataviewjs
// Step 1: Fetch all notes with valid period_progress values
const allNotes = dv
  .pages('"01_Daily"')
  .where(p => p.period_progress && ["started", "middle", "ended"].includes(p.period_progress));

// Step 2: Extract unique cycle numbers, sort them in descending order, and select the latest 3
const uniqueCycles = Array.from(new Set(allNotes.map(p => p.period_cycle))); // Ensure uniqueness
const lastThreeCycles = uniqueCycles.sort((a, b) => b - a).slice(0, 3); // Sort and take the latest 3

// Step 3: Filter notes for the latest 3 cycles
const filteredNotes = allNotes
  .where(p => lastThreeCycles.includes(p.period_cycle))
  .sort(p => [p.period_cycle, p.file.day]); // Sort by cycle and then by file day

// Step 4: Group the filtered notes by cycle
const groupedNotes = lastThreeCycles.map(cycle => ({
  cycle: cycle,
  notes: filteredNotes.filter(p => p.period_cycle === cycle),
}));

// Step 5: Display the table, showing all notes grouped by cycle
dv.header(2, "Information on the last 3 cycles");
groupedNotes.forEach(group => {
  dv.header(3, `Cycle: ${group.cycle}`);
  dv.table(
    ["Progress", "Flow", "Mood", "Pain", "File"],
    group.notes.map(note => [
      note.period_progress,
      note.period_flow,
      note.mood,
      note.pain,
      dv.fileLink(note.file.path),
    ])
  );
});

```
