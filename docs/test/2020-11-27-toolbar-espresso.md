---
title: "Тестирование action bar (Espresso)"
permalink: /docs/toolbar-espresso/
layout: single-withoutcaption
toc: true
layout: single
sidebar:
  nav: "docs"
---

* home button
* open navigation drawer
* open menu overflow


### Open navigation drawer 
```kotlin
fun openNavigationDrawer(): NavigationDrawerScreen {
    onView(ViewMatchers.withContentDescription("open"))
            .perform(click())
    return NavigationDrawerScreen(device)

}
```

### Press onBack button
```kotlin
fun clickOnHome() {
    onView(ViewMatchers.withContentDescription(R.string.abc_action_bar_up_description)).perform(click())
}
```


### Open menu overflow

! R.id.menu_nav - меню создаются в иерархии с другими id, так что для клика 
нужно использовать R.string

```kotlin
fun openSortScreen(){
    val menuSort = R.string.menu_sort
    openActionBarOverflowOrOptionsMenu(InstrumentationRegistry.getInstrumentation().targetContext)
    onView(withText(menuSort)).perform(click())
}
```
