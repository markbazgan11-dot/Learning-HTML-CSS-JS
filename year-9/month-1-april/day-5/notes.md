# Year 9 — Day 5

## What I Did
Today I focused on HTML forms and tables, covering input types, form structure, fieldsets, select dropdowns, radio buttons, checkboxes, and table anatomy. Three projects completed.

## Improvements
1. Built a hotel feedback form using `<form>`, `<fieldset>`, `<legend>`, `<input>`, `<select>`, `<textarea>` and `<button>`
2. Built a calculus grades table using `<thead>`, `<tbody>`, `<tfoot>`, `<caption>` and `colspan`
3. Built a book catalog table — note: `</body>` was placed before the `<table>` by mistake, putting the table outside the body (fix: move closing tags to the end)

---

## Active Recall

**Q1: What does the `for` attribute on a `<label>` do, and what must it match?**
A: The `for` attribute links a label to a specific input element. It must match the `id` of the input it belongs to. This means clicking the label will focus the input, which is important for accessibility and usability.

---

**Q2: How do you make radio buttons only allow one selection at a time?**
A: Give all the radio buttons in the group the same `name` attribute. The browser automatically groups them and enforces that only one can be selected at a time. Each button should still have a unique `id` and matching 
  `value`.

---

**Q3: What is the difference between `value` and the visible text inside a `<select>` option?**
A: The visible text is what the user sees in the dropdown. The `value` attribute is what actually gets sent to the server when the form is submitted. For example, the user sees "Very Good" but the server receives "very-good".

---

**Q4: What does `colspan="2"` do on a table cell?**
A: It makes that cell stretch across 2 columns instead of just 1. Commonly used in `<tfoot>` for summary rows — like an "Average Grade" label that spans the name columns so the number lines up with the grade column.

---

**Q5: What is the difference between `<thead>`, `<tbody>` and `<tfoot>`, and why use them?**
A: They are semantic groupings for table rows. `<thead>` contains the header row with column labels. `<tbody>` contains the main data rows. `<tfoot>` contains summary or total rows at the bottom. Using them makes the table
   more readable and helps browsers and screen readers understand the table structure.

---

## Reflection
Forms and tables are more involved than basic HTML structure. The trickiest part is remembering that `for` must match `id` exactly, and that radio buttons are grouped by `name` not by `id`. The book catalog bug (closing 
`</body>` too early) is a good reminder to always check closing tags are in the right place. Tables feel logical once you think of them in three layers: header, body, footer.

---

## Tomorrow
- Start CSS basics on freeCodeCamp (selectors, colors, fonts)
- Look at the box model — it comes up immediately when you start styling
- Push today's projects to GitHub under the correct year/month/day folder
