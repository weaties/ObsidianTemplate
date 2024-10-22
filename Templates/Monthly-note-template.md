--- 
title: {{DATE:YY}}W{{DATE:ww}} - weekly summary 
tags:
	#weeklysummary
	#{{DATE:YY}}/{{DATE:MM}}/W{{DATE:ww}}
	

--- 


# Summary


## what are my plans for the Month

## what did I complete this Month

## what did I not complete this Month

## What did I learn this Month

## Three Month look back

- Review the last three week summaries and see what you need to make sure you continue to be aware of.


## Key Take aways


```dataview
table KTA as "Key Take Aways"
from #{{DATE:YY}}/{{DATE:MM}}/W{{DATE:ww}} 
where contains(KTA, "")
sort file desc

```

## TODOs


```dataviewjs
function callout(text, type) {
    const allText = `> [!${type}]\n` + text;
    const lines = allText.split('\n');
    return lines.join('\n> ') + '\n'
}

const query = `
not done
tags do not include #to/read 
path does not include Templates
path does not include Christmas 2022

(starts before tomorrow) OR (no happens date)

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
tags include #to/read 
path does not include Templates

(starts before tomorrow) OR (no happens date)

show urgency
short mode
`;

dv.paragraph(callout('```tasks\n' + query + '\n```', 'Reading List'));
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
