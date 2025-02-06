---
created: 2024-01-20 13:27
last_modified: 2024-01-20 13:27
tags:
  - "#obsidn"
  - "#tasks"
  - "#plugins"
---
### 개요
- 할일을 관리 해주는 obsidian의 플러그인

### Global Filter
- check 항목중에 특정 태그를 선정하여 해당 태그가 있는 check항목만을 가져오도록 설정
### Dates
- ##### Due date 📅
	- 마감일 
	- property::due
- ##### Scheduled date ⏳
	- 작업을 수행할 계획이 있는 날짜
	- due 과 비슷하지만 schedule은 마감일 이전에 완료 할수 있다?
	- property::scheduled
- ##### Start date 🛫
	- 시작일
	- property::starts
- ##### created date ➕
	- task를 만든 날짜
	- property::created
- ##### Done date ✅
	- task를 완료한 날짜
	- property::done
- ##### Cancelled date
	- task를 취소한 날짜 ❌
	- proprty::cancelled
### Priority(우선순위)
1. 🔺 for highest priority
2. ⏫ for high priority
3. 🔼 for medium priority
4. use no signifier to indicate no priority
5. 🔽 for low priority
6. ⏬️ for lowest priority
### Recurring Tasks (반복)
- 🔁
>[!examples-]
>🔁 every 3 days
>🔁 every 10 days when done
>🔁 every weekday (meaning every Mon - Fri)
>🔁 every week on Sunday
>🔁 every week on Tuesday, Friday (meaning every Tuesday and Friday)
>🔁 every 2 weeks
>🔁 every 3 weeks on Friday
>🔁 every 2 months
>🔁 every month on the 1st
>🔁 every month on the last
>🔁 every month on the last Friday
>🔁 every month on the 2nd last Friday
>🔁 every 6 months on the 2nd Wednesday
>🔁 every January on the 15th
>🔁 every February on the last
>🔁 every April and December on the 1st and 24th (meaning every April 1st, April 24th, December 1st and December 24th)
>🔁 every year
### Status
- [ ] unchecked
- [/] in progress
- [x] Done  ✅ 2024-01-20 
- [-] Cancel ❌ 2024-01-20
- [p] pro
- [c] con
###### type
- TODO
- DONE
- IN_PROGRESS
- CANCELLED
- NON_TASK
### Queries
- 문법
>```tasks
>```

#### filters
##### 날짜필터
>```tasks
>on \<date> or \<date1> \#date1이거나 date2인 날
>before \<date> \#date 이전
>after \<date> 
>on or before \<date> \#date이거나 이전
>on or after \<date>
> ```

> [!NOTE] relative dates
>`yesterday`
>`today`
>`tomorrow`
>`next monday`
>`last friday`
>`14 days ago`
>`in two weeks`
>`14 October` (the current year will be used)
>`May` (1st May in the current year will be used)
###### 날짜 구간
>- `in <date range>` or `<date range>`
    - will match the **start** date, the **end** date and all dates in between.
    - `in` is the default for date range searches and may be omitted.
>- `before <date range>`
>	- will match all dates before the **start** date.
>- `after <date range>`
>	- will match all dates after the **end** date.
>- `in or before <date range>`
>	- will match the **end** date and all earlier dates.
>- `in or after <date range>`
>	- will match the **start** date and all later dates.
###### 날짜 속성 사용
- due date
- done date
- scheduled date
- start date
- created date
- cancelled date

> [!examples]
>- `no due date`
>- `has due date`
>- `due (on|before|after|on or before|on or after) <date>`
>- `due (in|before|after|in or before|in or after) <date range>`
>	- `YYYY-MM-DD YYYY-MM-DD`
>	- `(last|this|next) (week|month|quarter|year)`
>	- `(YYYY-Www|YYYY-mm|YYYY-Qq|YYYY)`
>- `due date is invalid`
>- `filter by function task.scheduled.format('dddd') === 'Wednesday'`

> [!info] start date가 없는 경우 필터링에 주의
> ```
> # Find tasks which start today or earlier: 
> ( (starts before tomorrow) AND (has start date) )
> ```
###### Happens
- start date, scheduled date, due date 을 검색함
##### text filter
>```tasks
>includes | does not includes \<search text> \# 대소문자 무시
>regex matches | does not regex matches \<javascript-style-regex>
>```
##### 조건 결합
> `AND` `NOT` `OR` `AND NOT` `OR NOT` `XOR`
##### status filter
###### name
>`filter by function task.status.name === 'DONE'`
###### type
>`status.type (is|is not) (TODO|DONE|IN_PROGRESS|CANCELLED|NON_TASK)`
###### symbol
>`filter by function task.status.symbol === '-'`
>`filter by function 'PCQA'.includes(task.status.symbol)`
##### properies filter
###### description
| Global Filter    | Task line                                                          | Text searched by description   |
|------------------|--------------------------------------------------------------------|--------------------------------|
| No global filter | '- [ ] Do stuff ⏫ #tag1 ✅ 2022-08-12 #tag2/sub-tag '               | `'Do stuff #tag1 #tag2/sub-tag'` |
| #task            | '- [ ] #task Do stuff ⏫ #tag1 ✅ 2022-08-12 #tag2/sub-tag '         | `'Do stuff #tag1 #tag2/sub-tag'` |
| global-filter    | '- [ ] global-filter Do stuff ⏫ #tag1 ✅ 2022-08-12 #tag2/sub-tag ' | `'Do stuff #tag1 #tag2/sub-tag'` |

> [!tip] decscriion tag 제거
> `task.descriptionWithoutTags`.

###### priority
- `priority is (above|below|not)? (lowest|low|none|medium|high|highest)`
- `filter by function task.priorityName !== 'Normal'`
- `filter by function task.priorityNumber % 2 === 0`
	- 0~5
###### Recurrence
- `is recurring`
- `is not recurring`
- `recurrence (includes|does not include) <part of recurrence rule>`
- `recurrence (regex matches|regex does not match) /<JavaScript-styleRegex>/`
- `filter by function task.isRecurring`
- `filter by function (!task.isRecurring) && task.originalMarkdown.includes('🔁')`
- `filter by function task.recurrenceRule.includes("every week") && task.recurrenceRule.includes("when done")`
###### Sub-items
`exclude sub-items`
###### tags
