---
title: "桌面自动化"
categories: [技术,自动化]
pin: false
---


### 编程方案（推荐）：
python库pyautogui、pywinauto方案可应对大多数桌面自动化需求

pyautogui：主要模拟鼠标键盘操作

pywinauto：基于Windows UI自动化框架，直接操作窗口控件



### RPA（机器人流程自动化）方案：

#### 主流工具：UiPath、Automation Anywhere、微软Power Automate等

Uipath studio元动作参数验证繁杂，适合大型复杂自动化需求

微软Power Automate软件设计较好，但仍存在流程壁垒，代码执行兼容不友好


## python实例

```python

from time import sleep

import pyautogui
from pywinauto.application import Application

app = Application().connect(path=r"C:/Program Files/WindowsApps/Microsoft.WindowsNotepad_11.2503.16.0_x64__8wekyb3d8bbwe/Notepad")

window= app['echo-Notepad']

window.type_keys("j")
# sleep(1)

# pyautogui.write("echo -e 'interface=wlan0\nssid=rv1126b\nhw_mode=a\nchannel=%信道%\nieee80211n=1\nieee80211ac=1\ndriver=nl80211\nbeacon_int=100' >  /etc/hostapd_5.8.conf")
pyautogui.press("enter")

```
