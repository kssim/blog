---
layout: post
title: D-Bus 란?
description: What is D-Bus?
original: https://www.freedesktop.org/wiki/Software/dbus/#index1h1
tags: [변역, D-bus]
---

# What is D-Bus?
D-Bus 는 메시지 버스 시스템으로 다른 어플리케이션과 통신하기 위한 간단한 방법입니다.  
그리고, D-Bus 는 프로세스의 라이프 사이클을 조정하는데도 도움이 됩니다.  
예를 들어, 단일 인스턴스 어플리케이션이나 데몬을 작성하거나, 서비스가 필요할 때, 어플리케이션이나 데몬을 시작하는 일을 쉽고 안정적으로 만들어줍니다.  


D-Bus 는 시스템 데몬과 사용자 로그인 세션별 데몬을 제공합니다.  
  * 시스템 데몬에서는 "새로운 하드웨어 장치의 추가" 나 "프린트 큐의 변화" 등의 이벤트를 위해서 사용합니다.  
  * 사용자 로그인 세션별 데몬은 사용자 어플리케이션 간의 일반적인 IPC를 위해 사용합니다.  

또한, 메시지 버스는 메시지 버스 데몬을 거치지 않고, 직접 통신 할 수 있는 두 개의 어플리케이션에서 사용될 수 있는 일반적인 1대1 메시지 전달 프레임 워크 위에 구축됩니다.  


D-Bus 의 [저수준 API 레퍼런스의 구현](https://dbus.freedesktop.org/doc/api/html/index.html)과 D-Bus [프로토콜](https://dbus.freedesktop.org/doc/dbus-specification.html)은 몇년 동안 실제 상황에서 많은 테스트가 이루어졌고, 이제 확정됐습니다.  
향후 변경 사항에 대해서는 적절하게 변경되거나 버전으로 구분될 예정입니다.  


저수준의 libdbus 레퍼런스 라이브러리는 의존성이 없습니다.  
레퍼런스 버스 데몬의 의존성은 XML 파서 하나 뿐입니다.  
고수준 바인딩 프레임워크(Qt, Glib, etc)들은 추가로 의존성을 가지고 있습니다.  
하지만, 더 많은 상황에 대비할 수 있고, 사용하기가 훨씬 쉽습니다.  

C#, Java, Ruby 와 같은 여러 언어들에서 D-Bus 프로토콜을 재구현한 라이브러리가 있습니다.  
이 라이브러리들은 libdbus 의 레퍼런스를 사용하지 않았습니다.  

저수준의 구현은 어플리케이션의 사용자를 중심으로 설계되지 않았습니다.  
오히려, 바인딩을 위한 사용자와 재구현을 위한 레퍼런스의 기반으로 사용됩니다.  
만약에 저수준과 고수준을 선택할 수 있다면, 고수준 바인딩이나 구현물을 사용하는 것을 권장합니다.  
이 목록은 [bindings page](https://www.freedesktop.org/wiki/Software/DBusBindings/) 에서 찾을 수 있습니다.  


[D-Bus 를 사용하는 프로젝트의 리스트](https://www.freedesktop.org/wiki/Software/DbusProjects/)는 늘어나고 있고, 다양한 API 의 사용 방법들을 제공하고 있습니다.  

D-Bus 는 Linux 나 Unix 계열에 이식성이 뛰어납니다. 그리고, Windows 로의 포팅은 진행중입니다.  
만약 D-Bus 를 사용하면서 문제가 있거나, 구현을 위한 아이디어가 있으면, 버그를 보고하고, 코멘트를 주세요.
