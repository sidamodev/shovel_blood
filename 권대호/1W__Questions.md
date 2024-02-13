---
status: backlog
published: false
done: false
type: [zettelkasten, capturing]
priority: 
title: 
tags:
    - 
duration: '`= choice(this.end, sum(date("2023-01-01T" + this.end) - date("2023-01-01T" + this.start)), "not finished")`'
ago: '`= choice((date(today) - date(this.date)).days = 0, "Today", choice((date(today) - date(this.date)).days >= 365, regexreplace(string(date(today) - date(this.date)), "\D\d?\d?", "") + " years ago", choice((date(today) - date(this.date)).days >= 31, regexreplace(string(date(today) - date(this.date)), "\D\d?d?", "") + " months ago", choice((date(today) - date(this.date)).days > 6, regexreplace(string(date(today) - date(this.date)), "\D\d?d?", "") + " weeks ago", choice((date(today) - date(this.date)).days > 0, regexreplace(string(date(today) - date(this.date)), "\D\d?d?", "") + " days ago", choice((date(today) - date(this.date)).days = -1, "tomorrow", regexreplace(string(date(this.date) - date(today)), "\D\d?\d?", "") + " days later"))))))`'
---

%%
date:: 2024-02-13
parents::
children::
related:: [[2024-02-13]]
summary:: ""
ref:: 
source:: 
%%

# [[1W__Questions]]

>[!abstract]
>Make note atomic.
>
>Point of capturing note is that I want get into the habit of capturing and if I feel the friction of, this is not atomic enough, not properly then less likely to capture notes as a habit. So you've given yourself the permission to just capture notes however you want to do it.
>
>This note should have Questions, Ideas, Supplementary tools. Question tags question, Ideas tags paradox or counter-intuitive and Supplementary tools tags quote, anecdote and scientific study.
>
>Status could be build(develop ideas), check(confirm idea, for accuracy, source, etc.), to-read and to-watch(find time to consume and take notes) as Input area. As output could  anything if you want to contribute or publish status could be magazine name or instagram etc.
>
>Title should be easy to find via keyword(general word). Putting the keywords that you think you will search for later down the line. 

# Idea:

1. array 요소에 접근하는 방법을 base reg addressing mode로 설명하세요
2. 주소 지정 방식 중 indirect addressing mode가 왜 immediated addressing mode와 direct addressing mode 보다 더 많은 데이터를 표현할 수 있는지, 명령어의 구조와 word를 연관지어 설명하세요.

# Bearing:

>[!info]
>There is four area, West, East, North, South. These based on Question, Evidence and Conclusion.
>West means What's similar to X. In this field supplementary tools and related concepts are involved.
>East means What's opposite of X. 
>North means Where X comes from. 
>South means Where X leads to.

## West: similar



## East: opposite



## North: theme / question

[[3.명령어]], [[4.CPU_작동_원리]], [[5.CPU_performance_improvement]]

## South: what does this lead to



# Sources
