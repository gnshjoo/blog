+++
title = "About gRPC 1"
date = 2021-02-26T22:09:23+09:00
tags = []
description = ""
featuredImage = ""
draft = true
+++

# gRPC 
---
구글에서 개발한 RPC(Remote Communication Mechanism) 시스템이다.
기본 RPC와 동일하지만 HTTP/2 기반으로 양방향 스트리밍을 지원하고 HTTP/2를 사용함으로써 메세지의 압축률과 성능이 좋다고 한다.

특징으로는 다양한 언어(C/C++/C#, Dart, Go, JAVA, Kotlin/JVM, Node.js, Objective-C, PHP, Python, Ruby) 등의 언어를 지원합니다.
gRPC는 서비스와 메시지를 정의하기 위해 Protocol Buffers를 사용한다. 



## Proto 
---
![Example image](/img/about-grpc-1.png)

```
    syntax 로 사용할 문법 버전을 선언

    package는 이름은 프로토콜 메시지 타입 사이의 이름 충돌을 방지하고자 사용

    service는 gRPC 서비스의 인터페이스를 정의하는데 사용

    message는 Product 정보의 메시지 형식/타입을 정의
```


## Source 생성
---
```shell
    protoc -I . <name>.proto --go_out=plugins=grpc:<module_dir_path>/<name>
```
소스 파일을 참조하는 proto파일을 생성. proto 컴파일러가 파일을 읽고 Go 파일을 생성한다.

![Example image](/img/grpc-2.png)

service 코드를 만들어야한다.

```
    server는 product_info를 구현하는데 사용

    AddProduct는 Product 추가 함수 구현

    GetProduct는 ProdcutID를 가져오는 함수 구현
```
