---
title: "Jira + Android Studio "
permalink: /docs/jira/
layout: single-withoutcaption
sidebar:
  nav: "docs"
---

### Настройка
Tools > Tasks & Contexts > Configure Servers…

Alt+Insert  >  select "Jira"

<img src="jira/jira-servers.png" width="300" alt="jira-servers">

| Server URL | https://companyname.atlassian.net                            |
| ---------- | ------------------------------------------------------------ |
| Email      | зарегистрированный в atlassian                               |
| API token  | [генерация в профиле](https://id.atlassian.com/manage/api-token) |
| Search     | поисковый запрос, для отображения задач

**Пример запроса**

assignee = currentUser() AND sprint in openSprints() AND resolution = Unresolved order by updated

**Проблемы**:

* в ubuntu >  подвигать границы окна, чтобы все поля были видны

### Работа в Android Studio

Tools > Tasks & Contexts > Open Task

* создается ветка
* создается change list
  
<img src="jira/jira-servers.png" width="300" alt="jira-servers">

Tools > Tasks & Contexts > close Task
* commit changes (message = title in task jira)
* обновление статуса в jira
  
  <img src="jira/android-close-task.png" width="300">

! Не корректная работа с плагином GitFlow, поэтому branch
нужно закрывать вручную через контекстное меню.

**Итоговый вид коммитов**

<img src="jira/android-history-commit.png" width="600">
