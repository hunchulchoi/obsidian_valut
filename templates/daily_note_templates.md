---
date_daily: daily_note
tags:
  - daily
important_date: 
한일:
---
<%*
const currentMoment = moment(tp.file.title, 'YYYY-MM-DD')
tR += `< [[${currentMoment.format('YYYY|YYYY년')}]] / [[${currentMoment.format('YYYY-MM|MM월')}]] / [[${currentMoment.format('gggg-[W]ww')}|${currentMoment.format('ww[주]')}]] >
`

const adds = currentMoment.day()===1?[-3, 3, 1]:currentMoment.day()===5?[-1,1,3]:[-1,1,1]
tR += `<< [[${currentMoment.add(adds[0], 'days').format('YYYY-MM-DD(ddd)')}]] 👈 |  [[${currentMoment.add(adds[1], 'days').format('YYYY-MM-DD(ddd)')}]] | 👉[[${currentMoment.add(adds[2], 'days').format('YYYY-MM-DD(ddd)')}]] >>`

currentMoment.add((adds[2]*-1), 'days')
%>

## 내일 기억할 일
> [!note]
> -
## 오늘 기억할 일
>[!info]
> 
<%*

const addDay = moment(tp.file.title, 'YYYY-MM-DD').day() ==1?-3:-1

const yesterday = `10. Planner/11. Daily/${tp.date.now('YYYY-MM-DD(ddd)', addDay, tp.file.title, 'YYYY-MM-DD')}`
const section = '## 내일 기억할 일'
let sectionContent = ''

let yfile = tp.file.find_tfile(yesterday)
if(yfile){
	const content = await app.vault.read(yfile)
	if(content.includes(section)){
		const startIndex = content.indexOf(section) + section.length
		let endIndex = content.indexOf('\n##', startIndex)
		endIndex = endIndex === -1?content.length:endIndex;
		
		sectionContent = content.substring(startIndex, endIndex).trim()
		sectionContent = sectionContent.replaceAll('> [!note]\n', '')
		console.log(`sectionContent:'${sectionContent}'`)
		if(sectionContent==='> -') sectionContent = ''
	}
}

tR += sectionContent || '없습니다.😅'
%>

### 오늘의 할일
> [!todo]
>  - [ ]
### 할일 추가하기
> [!todo]
> - [ ]

### 오늘 끝내야 할일
```tasks
due on or before <% tp.file.title.slice(0,10) %>
  filter by function task.file.folder.includes('10. Planner')
  filter by function !task.file.folder.includes('templates')
  not done
  sort by priority
```

### 이번주 할일
```tasks
due on or before <% moment(tp.file.title.slice(0,10), 'YYYY-MM-DD').weekday(7).format('YYYY-MM-DD') %>
  filter by function task.file.folder.includes('10. Planner')
  filter by function !task.file.folder.includes('templates')
  not done
  sort by priority
```

### 언젠가 할일
```tasks
no due date
not done
filter by function task.file.folder.includes('10. Planner')
description regex does not match /^$/
```
### 사건
> [!warning]
>  -
