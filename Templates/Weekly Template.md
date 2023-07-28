# <%moment(tp.file.title).startOf('isoWeek').format("MMM DD") %> ~ <%moment(tp.file.title).endOf('isoWeek').format("MMM DD") %>

[[Journal/Weekly/<%moment(tp.file.title).subtract(1, 'week').format("gggg-[W]ww")%>|⇠ Previous Week]] | [[Journal/Weekly/<%moment(tp.file.title).add(1, 'week').format("gggg-[W]ww")%>|Next Week ⇢]]

# Overview

```dataview
table without id
	file.link AS "Day",
	sleep AS "🛌",
	choice(tasks, "☑", "☐") AS "📝",
	choice(read, "☑", "☐") AS "📚",
	choice(exercise, "☑", "☐") AS "🏃‍♂️",
	choice(clean, "☑", "☐") AS "🧹",
	choice(language, "☑", "☐") AS "🔠",
	choice(meditate, "☑", "☐") AS "🧘‍♂️",
	choice(journal, "☑", "☐") AS "📓",
	choice(math, "☑", "☐") AS "🧮"
from "Journal/Daily"
where week = "<%moment(tp.file.title).format("gggg-[W]ww")%>"
```