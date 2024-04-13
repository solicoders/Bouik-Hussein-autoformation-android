2. Windows: Verify system requirements
Android Studio system requirements
The following are the system requirements for Android Studio on Windows.

64-bit Microsoft® Windows® 8/10/11
x86_64 CPU architecture; 2nd generation Intel Core or newer, or AMD CPU with support for a Windows Hypervisor
8 GB RAM or more
8 GB of available disk space minimum (IDE + Android SDK + Android Emulator)
1280 x 800 minimum screen resolution
Check system requirements (Windows 10)
On a Windows computer, you can find all the information that you need to verify the system requirements in the Settings app.

Open Settings.
Tip: You can use the search tool next to the Start button at the bottom of your screen to locate it.

Click System.
At the bottom of the left-hand navigation pane, click About.
Make sure that the Windows specifications meet or exceed the requirements. e37a2f51fc945235.png
Select Device specifications. Make sure that the Installed RAM is at least as much as is required and that the system type is the 64-bit version of the operating system.
d57ac05cc5c74047.png

In the navigation pane, click Display. Make sure that the Resolution is the same or better than what's required.
45f3ba97421c68e0.png

Verify storage
Open the file explorer.
In the left-hand navigation pane, click This PC.
Ensure that the local storage has enough free space to install Android Studio.
4748e8a455b8cdba.png

Check system requirements (Windows 8.1)
If you're using Windows 8.1, the steps to find device specifications are as follows:

Open the Settings App.
In the navigation pane, click PC and devices.
In the navigation pane, click PC info. Check that your CPU and RAM meet the minimum requirements, and ensure you're using a 64-bit operating system.
71f9a2e30fb16593.png

In the navigation pane, click Display. Check that your display meets the requirements. 97c48dd5bda38ee7.png
Open the file explorer, click This PC, and check that you have enough disk space. 19ab36acd1dbffea.png

3. Windows: Download and install Android Studio
Download Android Studio
Open any web browser and navigate to the Android Studio download page.
This is the Android Developers website, where you can download Android Studio. This page automatically detects your operating system.

Click Download Android Studio. The Terms and Conditions page with the Android Studio License Agreement opens.
Read the License Agreement.
At the bottom of the page, if you agree with the terms and conditions, select the I have read and agree with the above terms and conditions checkbox.
Click Download Android Studio to start the download.
When prompted, save the file to a location where you can easily locate it, such as the Downloads folder.
Wait for the download to complete. This may take a while and may be a good moment to enjoy some tea!
Install Android Studio on Windows
Open the folder where you downloaded and saved the Android Studio installation file.
Double-click the downloaded file.
If you see a User Account Control dialog about allowing the installation to make changes to your computer, click Yes to confirm the installation.
d01a8cfe00b9b80b.png

The Welcome to Android Studio Setup dialog displays.

82d03b4157cdc3ad.png

Click Next to start the installation.
Accept the default installation settings for all steps.
Click Finish when the installation is done to launch Android Studio.
6a7eba659ca0d6f1.png

Choose your preference of light or dark theme when Android Studio first launches. Screenshots in this course use the light theme, but choose whichever one you prefer.
e91289b2f9f25157.png

During the installation, the setup wizard downloads and installs additional components and tools needed for Android app development. This may take some time depending on your internet speed. During this time, you may see a User Account Control dialog for Windows Command Processor. Click Yes to accept the dialog.
22f23c1915646d8f.png

You may also receive a Windows Security Alert about adb.exe. Click Allow Access, if needed, to continue the installation.
785f9241b5a8f766.png

When the download and installation completes, click Finish.
The Welcome to Android Studio window displays and you're ready to start creating apps!

Create your first Android app
About this codelab
subjectLast updated Apr 12, 2024
account_circleWritten by Google Developers Training team
1. Before you begin
Install Android Studio on your computer if you haven't done so already. Check that your computer meets the system requirements required for running Android Studio (located at the bottom of the download page). If you need more detailed instructions on the setup process, refer to the Download and install Android Studio codelab.

In this codelab, you create your first Android app with a project template provided by Android Studio. You use Kotlin and Jetpack Compose to customize your app. Note that Android Studio gets updated and sometimes the UI changes so it is okay if your Android Studio looks a little different than the screenshots in this codelab.

Prerequisites
Basic Kotlin knowledge
What you'll need
The latest version of Android Studio
What you'll learn
How to create an Android App with Android Studio
How to run apps with the Preview tool in Android Studio
How to update text with Kotlin
How to update a User Interface (UI) with Jetpack Compose
How to see a preview of your app with Preview in Jetpack Compose
What you'll build
An app that lets you customize your introduction!
Here's what the app looks like when you complete this codelab (except it will be customized with your name!):

13957184d295b16f.png

What you'll need
A computer with Android Studio installed.
