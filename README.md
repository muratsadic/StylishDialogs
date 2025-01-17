
[![](https://jitpack.io/v/MarsadMaqsood/StylishDialogs.svg)](https://jitpack.io/#MarsadMaqsood/StylishDialogs)


Stylish Alert Dialog
===================
Stylish Alert Dialogs for Android.

### Features
- Ability to set custom view
- More convenient interface to bind listeners (like in AlertDialog)
- Third neutral button with own listener, colors, methods and etc.
- Ability to disable buttons
- Ability to set buttons stroke width
- Dark style of dialogs
- Ability to make dialogs without buttons
- Support of HTML tags
- Ability to set text size
- Ability to set color of buttons

### Upcoming Dialog Designs
- Text Bouncing Dialog

### Screenshot
![image](https://github.com/MarsadMaqsood/StylishDialogs/blob/master/assets/sample_1.gif)

**Maven**

	<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>

	<dependency>
	    <groupId>com.github.MarsadMaqsood</groupId>
	    <artifactId>StylishDialogs</artifactId>
	    <version>0.1.+</version>
	</dependency>

**Gradle**

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

	dependencies {
	        implementation 'com.github.MarsadMaqsood:StylishDialogs:1.0.+'
	}

## How to Usage

Show simple material progress

**Java**
```java
StylishAlertDialog stylishDialog = new StylishAlertDialog(this, StylishAlertDialog.PROGRESS);
stylishDialog.getProgressHelper().setBarColor(Color.parseColor("#A5DC86"));
pDialog.setTitleText("Loading")
       .setCancellable(false)
       //.setCancelledOnTouchOutside(false)
       .show();

```
---
**Kotlin**
```kotlin
val pDialog = StylishAlertDialog(this, StylishAlertDialog.PROGRESS)
pDialog.progressHelper.barColor = Color.parseColor("#A5DC86")
pDialog.setTitleText("Loading")
       .setCancellable(false)
       //.setCancelledOnTouchOutside(false)
       .show()

```


You can customize progress bar dynamically with the materialish-progress methods via
```java
StylishAlertDialog.getProgressHelper();
```
```java
resetCount()
isSpinning()
spin()
stopSpinning()
getProgress()
setProgress(float progress)
setInstantProgress(float progress)
getCircleRadius()
setCircleRadius(int circleRadius)
getBarWidth()
setBarWidth(int barWidth)
getBarColor()
setBarColor(int barColor)
getRimWidth()
setRimWidth(int rimWidth)
getRimColor()
setRimColor(int rimColor)
getSpinSpeed()
setSpinSpeed(float spinSpeed)
getButton(/*StylishAlertDialog.Button)Type*/)
getButton(/*StylishAlertDialog.Button)Type*/).setBackgroundTintList()
setCancellable(boolean cancellable)
setCancelledOnTouchOutside(boolean cancelledOnTouchOutside)
setCustomView(View view, boolean withContent)
setDismissOnClick(boolean dismissOnClick)
```

Code Samples
---

Simple basic message：

**Java**
```java
    new StylishAlertDialog(this)
            .setTitleText("Here's a message!")
            .show();
```
___
**Kotlin**
```kotlin
    StylishAlertDialog(this)
        .setTitleText("Here's a message!")
        .show()
```
Title with a text under：

**Java**
```java
    new StylishAlertDialog(this)
            .setTitleText("Here's a message!")
            .setContentText("It's pretty, isn't it?")
            .show();
```
___
**Kotlin**
   ```kotlin
    StylishAlertDialog(this)
        .setTitleText("Here's a message!")
        .setContentText("It's pretty, isn't it?")
        .show()
```
Error message：

**Java**
```java
    new StylishAlertDialog(this, StylishAlertDialog.ERROR)
            .setTitleText("Oops...")
            .setContentText("Something went wrong!")
            .show();
```
---
**Kotlin**
```kotlin
    StylishAlertDialog(this, StylishAlertDialog.ERROR)
        .setTitleText("Oops...")
        .setContentText("Something went wrong!")
        .show()
```

Warning message：

**Java**
```java
    new StylishAlertDialog(this, StylishAlertDialog.WARNING)
            .setTitleText("Are you sure?")
            .setContentText("Won't be able to recover this file!")
            .setConfirmText("Yes, delete it!")
            .show();
```
---
**Kotlin**
```kotlin
    StylishAlertDialog(this, StylishAlertDialog.WARNING)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes, delete it!")
        .show()
```
Success message：

**Java**
```java
    new StylishAlertDialog(this, StylishAlertDialog.SUCCESS)
            .setTitleText("Good job!")
            .setContentText("You clicked the button!")
            .show();
```
---
**Kotlin**
```kotlin
    StylishAlertDialog(this, StylishAlertDialog.SUCCESS)
        .setTitleText("Good job!")
        .setContentText("You clicked the button!")
        .show()
```
Message with a custom icon：

**Java**
```java
    new StylishAlertDialog(this, StylishAlertDialog.CUSTOM_IMAGE)
            .setTitleText("Stylish!")
            .setContentText("Here's a custom image.")
            .setCustomImage(R.drawable.custom_img)
            .show();
```
---
**Kotlin**
```kotlin
    StylishAlertDialog(this, StylishAlertDialog.CUSTOM_IMAGE)
        .setTitleText("Stylish!")
        .setContentText("Here's a custom image.")
        .setCustomImage(R.drawable.custom_img)
        .show()
```
Message with a custom view：

**Java**
```java
    final EditText editText = new EditText(this);
    new StylishAlertDialog(this, StylishAlertDialog.NORMAL)
            .setTitleText("Custom view")
            .setConfirmText("Ok")
            .setCustomView(editText)
            .show();
```
---
**Kotlin**
```kotlin
    val editText = EditText(this)
    StylishAlertDialog(this, StylishAlertDialog.NORMAL)
        .setTitleText("Custom view")
        .setConfirmText("Ok")
        .setCustomView(editText)
        .show()
```

Different ways to bind the listener to button：

**Java**

```java
    new StylishAlertDialog(this, StylishAlertDialog.WARNING)
                .setTitleText("Are you sure?")
                .setContentText("Won't be able to recover this file!")
                .setConfirmText("Yes,delete it!")
                .setConfirmClickListener(new StylishAlertDialog.OnStylishClickListener() {
        @Override
        public void onClick(StylishAlertDialog sDialog) {
            sDialog.dismissWithAnimation();
        }
    })
            .setCancelButton("Cancel", new StylishAlertDialog.OnStylishClickListener() {
        @Override
        public void onClick(StylishAlertDialog sDialog) {
            sDialog.dismissWithAnimation();
        }
    }).show();
```
---
**Kotlin**
```kotlin
    StylishAlertDialog(this, StylishAlertDialog.WARNING)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .setConfirmClickListener(StylishAlertDialog::dismissWithAnimation)
        .setCancelButton("Cancel",StylishAlertDialog::dismissWithAnimation)
        .show()
```
Disable button

**Java**
```java
    new StylishAlertDialog(this, StylishAlertDialog.WARNING)
                .setTitleText("Are you sure?")
                .setContentText("Won't be able to recover this file!")
                .setConfirmText("Yes, delete it!")
                .setConfirmClickListener(new StylishAlertDialog.OnStylishClickListener() {
        @Override
        public void onClick(StylishAlertDialog sDialog) {
            sDialog
                    .setTitleText("Deleted!")
                    .setContentText("Your imaginary file has been deleted!")
                    .setConfirmText("OK")
                    .setConfirmClickListener(null)
                    .changeAlertType(StylishAlertDialog.SUCCESS);
        }
    }).show();

```
---
**Kotlin**
```kotlin
    val disabledBtnDialog = StylishAlertDialog(this, StylishAlertDialog.NORMAL)
        .setTitleText("Title")
        .setContentText("Disabled button dialog")
        .setConfirmText("Confirm")
        .setCancelText("Cancel")
        disabledBtnDialog.setOnShowListener {
            disabledBtnDialog.getButton(StylishAlertDialog.BUTTON_CONFIRM).isEnabled = false
        }
        disabledBtnDialog.show()

```

**Change** the dialog style upon confirming：

**Java**

```java
    new StylishAlertDialog(this, StylishAlertDialog.WARNING)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes, delete it!")
        .setConfirmClickListener(new StylishAlertDialog.OnStylishClickListener() {
            @Override
            public void onClick(StylishAlertDialog sDialog) {
                sDialog
                    .setTitleText("Deleted!")
                    .setContentText("Your imaginary file has been deleted!")
                    .setConfirmText("OK")
                    .setConfirmClickListener(null)
                    .changeAlertType(StylishAlertDialog.SUCCESS);
            }
        })
        .show();
```
---
**Kotlin**
```kotlin

        StylishAlertDialog(this, StylishAlertDialog.WARNING)
            .setTitleText("Are you sure?")
            .setContentText("Won't be able to recover this file!")
            .setConfirmText("Yes, delete it!")
            .setConfirmClickListener { sDialog ->
                sDialog.setTitleText("Deleted!")
                    .setContentText("Your imaginary file has been deleted!")
                    .setConfirmText("OK")
                    .setConfirmClickListener(null)
                    .changeAlertType(StylishAlertDialog.SUCCESS)
            }
            .show()
```


**Proguard-Rules**
```pro
-keep class com.marsad.stylishdialogs.RotatingAnimation {
	    public <init>(...);
}
```


## License

    The MIT License (MIT)

	Copyright (c) 2021 Marsad Maqsood

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
