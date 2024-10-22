---

company:

location:

title:

email:

website:

aliases:

---

tags:: [[People MOC]]

# <% tp.file.title %>

<% await tp.file.move("/People/" + tp.file.title) %>

## Notes

-

## Meetings

```dataview

TABLE file.cday as Created, KTA AS "KTA"

FROM "01Weekly" where contains(file.outlinks, [[<% tp.file.title %>]])

SORT file.cday DESC

```