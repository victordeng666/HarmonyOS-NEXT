# Understand HarmonyOS NEXT's IDE - DevEco Studio
## introduce
HUAWEI DevEco Studio (click the link to download the tool, hereinafter referred to as DevEco Studio) is built on the open source version of IntelliJ IDEA Community, providing a one-stop development platform for applications and meta services (hereinafter referred to as applications/meta services) running on the HarmonyOS system.

As a development tool, DevEco Studio not only has basic functions such as code development, compilation, construction, and debugging, but also has the following features:
Efficient and intelligent code editing: Supports code highlighting, intelligent code filling, code error checking, automatic code jumping, code formatting, code searching, and other functions in languages such as ArkTS, JS, C/C++to improve code writing efficiency. For more detailed information, please refer to the code editor.
Multi terminal bidirectional real-time preview: supports bidirectional preview, real-time preview, dynamic preview, component preview, and multi terminal device preview of UI interface code, making it easy to quickly view the code running effect. For more detailed information, please refer to the interface preview.
Multi terminal device simulation: Provides HarmonyOS local simulator, supports simulation of devices such as Phone, and provides convenient access to debugging environment. For more detailed information, please refer to using emulators to run applications/meta services.
DevEco Profiler Performance Optimization: Provides real-time monitoring capabilities and scenario based optimization templates, facilitating comprehensive device resource monitoring, collecting data covering multiple dimensions, and providing developers with an efficient and straight through code line optimization experience. Please refer to performance analysis.

## Customized configuration
Set theme:
Set Simplified Chinese

## IDE interface introduction
The entire IDE interface can be roughly divided into four parts

At the bottom of the notification bar, there is a toolbar that mainly introduces commonly used items
Build: Output information when building a project
Problems: Error and Reminder Information Bar
Terminal: Command line terminal, where command line operations are executed
PreviewerLog: PreviewerLog
Log: The logs generated during the operation of the simulator and the real machine

The previewer provides some basic functions, including rotating the screen, switching display devices, and multi device preview.
Click the rotation button to switch between vertical and horizontal display effects.

Common problem: If preview fails, click "Refresh"

You can also click the following list button to switch the displayed device types.

The pop-up box will display Available profiles, which are the available device types.
If you click on the Foldable to switch devices, you can also click the rotation button to switch between the horizontal and vertical display modes of the Foldable.
Turn on the Muti profile preview switch to enable real-time preview of devices of multiple sizes.

Click the "Reviewer" button in the upper right corner of the previewer to open the component review interface

Click on the component, the preview area will display the basic properties of the component, and the code editing area will box the code corresponding to the component


## Quick Start
Select "Help" → "Quick Start"

In this panel, there will be some quick start experiment guides and some commonly used links.
Quick Start is like a bookmark, presenting the most commonly used learning resources to developers to help them better learn HarmonyOS application development.

## Built in documents
Hover over the component and click on 'Show in API Reference'


## Code Search
Search for the content of the current file: Ctrl+F
Search and replace content: Ctrl+R

Search for all content in the project:
By pressing the Shift shortcut key twice in a row, the code search interface can be opened. Double clicking the search result can quickly open the location of the file.


## Common shortcut keys
Common shortcut keys	describe
Ctrl + F	Search for the content of the current file
Ctrl + R	Search and replace content
Press the Shift shortcut key twice in a row	Search for all content in the project
Ctrl + Alt + L	formatting code
Ctrl + /	Code single line comments//
Ctrl + Shift + /	Multi line code comments/**/
Ctrl + Mouse click	Jump source code and files

common problem:
The shortcut keys for formatting code conflict with the latest version of QQ shortcut keys. Simply disable QQ shortcut keys
