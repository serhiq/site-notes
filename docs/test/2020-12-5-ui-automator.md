---
title: "UI automator"
permalink: /docs/ui-automator/
layout: single-withoutcaption
sidebar:
  nav: "docs"

---
- Change the device rotation.
- Press a hardware key, such as "volume up".
- Press the Back, Home, or Menu buttons.
- Open the notification shade.
- Take a screenshot of the current window.

## Set up UI Automator

```groovy
dependencies {
    ...
    androidTestImplementation 'androidx.test.uiautomator:uiautomator:2.2.0'
}
```


## Inspect the UI on a device

To launch the `uiautomatorviewer` tool:

1. Launch the target app on a physical device.

2. Connect the device to your development machine.

3. Open a terminal window and navigate to the `<android-sdk>/tools/` directory.

4. Run the tool with this command:

   ```
   $ uiautomatorviewer
   ```

## Использование

```kotlin
  private val device = UiDevice.getInstance(InstrumentationRegistry.getInstrumentation())

  device.pressBack()
```


**Link by Google**

com.example.android.testing.uiautomator.BasicSample;

https://developer.android.com/training/testing/ui-automator

https://developer.android.com/training/testing/ui-testing/uiautomator-testing

https://developer.android.com/training/testing/ui-automator#accessing-device-state

Старый тренинг гугла, с подробным объяснением

https://google-developer-training.github.io/android-developer-fundamentals-course-concepts/en/Unit%202/61_c_testing_the_user_interface.html#auto

https://google-developer-training.github.io/android-developer-fundamentals-course-practicals/en/Unit%202/61_p_use_espresso_to_test_your_ui.html


**Staff**

https://proandroiddev.com/testing-android-notifications-f147a572b257

https://alexilyenko.github.io/uiautomator-basics/

**Open sourse которые использютт**

com.escodro.alkaa-   отключение анимации на устройстве для тестов
plaid  - open source
simple note - для скриншотного теста
tddweatherapp

**5 - как я использую в приложениях**

самый типичный случай -  тестирование rotation and onbackPressed, вместе с espresso тестами

=====

**Похожие библиотеки**

https://docs.fastlane.tools/actions/screengrab/

для создания скриншотов в разных locale, на разных устройствах


****

data/user/**pacaget**/files


Device file explorer 

Если не отображает скрины, нужно сделать
щелкнуть по папке
вызвать контекстное меню
нажать на *syncronise*

**Делаем скрины во время тестов**
1) подключить UI automator
2)  
   screenshot("01_open_app")


```kotlin
@Throws(Exception::class)
  fun screenshot(screenshotName: String) {
    val context: Context =
            InstrumentationRegistry.getInstrumentation().getTargetContext().getApplicationContext()
    val e: File = context.filesDir
    val screenshotFileName = System.currentTimeMillis().toString() + "_" + screenshotName + ".png"
    val screenshotFile = File(e, screenshotFileName)
     device.takeScreenshot(screenshotFile)
  }
```
взято отсюда

https://github.com/fastlane/fastlane/issues/2080

3) в Android Studio , смотрим через device exploer, копируем


**Возможные проблемы**
сначала смотрим логи


api 23  requiare run-time permission

медленно работает app, скрин - сделан наполовину
добавить перед скринами задержку потока

```kotlin
    Thread.sleep(300)
```







