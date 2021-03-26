---
title: "Feature test"
permalink: /docs/feature-test/
layout: single-withoutcaption
sidebar:
  nav: "docs"
  
---

Тесты значимых функций приложения

fun canLoginUsigEmail()
fun canRegisterAccount()
fun canRemoveAccount()
canRegisterUser
canHandleInvalidInput
canRelayDocumentBetweenServers
canCreateSchema
canLoginUsingWebService
canLoginUsingBasicAuth
canDeleteDocument
canAddDocument

**Стек технологий:**

Espresso, UI automator, Spoon (запуск одновременно на всех устройствах подключенных к adb и генерация отчета), Falcon (делаем скрины ошибок, либо ключевых позиций)


**Пример теста из UI automator sample**

```kotlin
  @Test
  fun canLoginUsingEmail() {
    val d= RotoDevice(device)
    screenShot("welcome")
    

    val s=d.openWelcome().signInWithEmail()
    screenShot("sign_in_empty")
      
    s.inputEmail(email)
    s.inputPassword(password)
    screenShot("sign_in_email_fill")
      
    val a=s.enter()
    screenShot("account_after_sign_in")
      
    d.checkOpen(RotoDevice.type.ACCOUNT)
    assertTrue(a.emailOnScreen==email)

  }
```

Очень хорошо работате в связке с page object - когда на каждый фрагмент, для читаемости кода создается вспомогательный класс.





