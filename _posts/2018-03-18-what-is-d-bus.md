---
layout: post
title: D-Bus 란?
description: What is D-Bus?
original: https://www.freedesktop.org/wiki/Software/dbus/#index1h1
tags: [번역, D-bus]
---

## What is D-Bus?
D-Bus 는 메시지 버스 시스템입니다. 이 녀석을 이용하면, 다른 어플리케이션과 간단하게 통신할 수 있습니다.  
그리고, D-Bus 는 프로세스의 Life cycle 관리에도 사용됩니다.  
예를 들어, 단일 인스턴스 어플리케이션이나 데몬 코드를 작성할 때, D-Bus 를 사용해서 쉽고 안정적으로 만들 수 있습니다.  
On-demand 로 실행되는 어플리케이션이나 데몬을 실행할 때도 D-Bus 를 사용하면, 같은 효과를 얻을 수 있습니다.  

<br/>

D-Bus 는 두가지 데몬을 제공합니다.  
1. System daemon (시스템 데몬)  
  * "새로운 하드웨어 장치의 추가" 나 "프린트 큐의 변화" 등 시스템 이벤트를 처리하기 위한 용도입니다.  
2. Per-user-login-session daemon (사용자 로그인 세션별 데몬)  
  * 사용자 어플리케이션 간의 일반적인 IPC 를 위한 용도입니다.  

그리고, D-Bus 의 메시지 버스는 일반적인 1:1 메시지 전달 프레임워크로 구축됩니다.  
이런 프레임워크들은 따로 메시지 버스 데몬을 거치지 않아도, 두 개의 어플리케이션이 직접 통신할 수 있도록 해줍니다.  

<br/>

D-Bus 의 [저수준 API 레퍼런스의 구현](https://dbus.freedesktop.org/doc/api/html/index.html)과 D-Bus [프로토콜](https://dbus.freedesktop.org/doc/dbus-specification.html)은 몇년 동안 실제 상황에서 혹독한 검증을 거쳐 완성됐습니다.   
이후, 변경 사항에 대해서는 호환성을 유지하거나, 버전으로 구분할 예정입니다.  

<br/>

저수준의 libdbus 레퍼런스 라이브러리는 의존성이 없습니다.  
레퍼런스 버스 데몬의 의존성은 XML 파서 하나 뿐입니다.  

일부 고수준 라이브러리(Qt, Glib, etc)들은 몇개의 의존성을 가지고 있습니다.  
하지만, 다양한 환경을 가정해서 만들어졌기 때문에 사용하기가 더 편리합니다.  
저수준의 libdbus 로부터 파생된 고수준 라이브러리들은 잘다듬어져있고, ABI 에 대해 안정적입니다.  


C#, Java, Ruby 와 같은 여러 언어들에서도 D-Bus 프로토콜을 재구현한 라이브러리가 있습니다.  
이 라이브러리들은 libdbus 의 레퍼런스를 사용하지 않습니다.  

<br/>

저수준으로 구현된 레퍼런스는 어플리케이션의 사용자를 중심으로 설계되지 않았습니다.  
이는 고수준 라이브러리로 바인딩을 하기 위한 레퍼런스나 바인딩을 하는 사용자를 위해 작성됐습니다.  
만약에 저수준 라이브러리와 고수준 라이브러리를 선택할 수 있다면, 고수준 라이브러리를 사용하는 것을 권장합니다.  
고수준 라이브러리의 목록은 [bindings page](https://www.freedesktop.org/wiki/Software/DBusBindings/) 에서 찾을 수 있습니다.  

<br/>

[D-Bus 를 사용하는 프로젝트의 리스트](https://www.freedesktop.org/wiki/Software/DbusProjects/)는 늘어나고 있고, 다양한 API 와 사용 방법들을 제공하고 있습니다.  
D-Bus 는 Linux 나 Unix 계열에 이식성이 뛰어납니다. 그리고, Windows 로의 포팅은 진행중입니다.  
