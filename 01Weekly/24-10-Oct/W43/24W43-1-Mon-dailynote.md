
# 2024-10-21



`dice: [[Daily Quotes]]`

## Summary

### TODO

### Happenings

## Key Take aways

```dataview
table KTA as "Key Take Aways"
from #24/10/W43/1 
where contains(KTA, "")
sort file desc

```


## Tasks

```dataviewjs

function callout(text, type) {
    const allText = `> [!${type}]\n` + text;
    const lines = allText.split('\n');
    return lines.join('\n> ') + '\n'
}

const query = `
not done
path does not include Templates

(starts before tomorrow) OR (no happens date) OR (due before tomorrow)

show urgency
short mode
`;

dv.paragraph(callout('```tasks\n' + query + '\n```', 'todo today'));
```


```dataviewjs

function callout(text, type) {
    const allText = `> [!${type}]\n` + text;
    const lines = allText.split('\n');
    return lines.join('\n> ') + '\n'
}

const query = `

not done
happens after tomorrow
path does not include Templates
short mode
show urgency`;

dv.paragraph(callout('```tasks\n' + query + '\n```', 'todo in the future'));


```


## Daily writings


| time | entry | role |
| ---- | ----- | ---- |








