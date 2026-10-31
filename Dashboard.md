---
type: dashboard
tags: [dashboard]
---

# 📚 Library Dashboard

> [!info] How to use
> Books live in `Books/` with a `status` and `tier` in frontmatter. Edit those fields and the tables below update automatically.
> Requires the **Dataview** community plugin.

## 📊 Overview

```dataview
TABLE length(rows) AS "Books"
FROM "Books"
WHERE type = "book"
GROUP BY status
SORT status ASC
```

## 📖 Currently Reading

```dataview
TABLE author, started, file.link AS "Book"
FROM "Books"
WHERE status = "reading"
SORT started DESC
```

## ✅ Read

```dataview
TABLE author, rating, tier, finished, file.link AS "Book"
FROM "Books"
WHERE status = "read"
SORT finished DESC
```

## 🔖 Want to Read

```dataview
TABLE author, genre, file.link AS "Book"
FROM "Books"
WHERE status = "want-to-read"
SORT file.name ASC
```

## 🗑️ Dropped

```dataview
TABLE author, file.link AS "Book"
FROM "Books"
WHERE status = "dropped"
```

## 🏆 Tier List

> [!tip] Tiers
> **S** masterpiece · **A** excellent · **B** good · **C** mixed · **D** not for me. See [[Tier List]].

```dataview
TABLE WITHOUT ID tier AS "Tier", file.link AS "Book", rating AS "Rating"
FROM "Books"
WHERE type = "book" AND tier
SORT tier ASC, rating DESC
```

## 📝 Recent Reviews

```dataview
TABLE book, rating, file.link AS "Review"
FROM "Reviews"
WHERE type = "review"
SORT file.mtime DESC
LIMIT 5
```

## 🧠 Recent Reading Notes

```dataview
TABLE book, chapter, date
FROM "Reading Notes"
WHERE type = "reading-note"
SORT date DESC
LIMIT 5
```

---
Related: [[Tier List]] · [[Templates/Book|New book]] · [[Templates/Review|New review]] · [[Templates/Reading Note|New note]]
