---
title: "golang 반복문"
date: 2020-10-03T19:04:45+09:00
draft: true
categories: ["TIL"]
tags: ["go"]
cover: ""
draft: false
---

# 1. Head First GO 게임

```go
package main

import (
	"bufio"
	"fmt"
	"log"
	"math/rand"
	"os"
	"strconv"
	"strings"
	"time"
)

func main() {
	seconds := time.Now().Unix()
	rand.Seed(seconds)
	target := rand.Intn(100) + 1
	fmt.Println("I've chosen a random number between 1 and 100.")
	fmt.Println("Can you guess it?")

	reader := bufio.NewReader(os.Stdin)
	success := false
	for guesses := 0; guesses < 10; guesses++ {
		fmt.Println("You have", 10-guesses, "guesses left")

		fmt.Println("Make a guess:")
		input, err := reader.ReadString('\n')
		if err != nil {
			log.Fatal(err)
		}
		input = strings.TrimSpace(input)
		guess, err := strconv.Atoi(input)
		if err != nil {
			log.Fatal(err)
		}
		if guess < target {
			fmt.Println("LOW")
		} else if guess > target {
			fmt.Println("HIGH")

		} else if guess == target {
			success = true
			fmt.Println("Success")
			break
		}
	}
	if !success {
		fmt.Println("you're failed, its", target)
	}

}


```

**_import package_**

- bufio : bufio Buffered I/O를 뜻한다. io.Reader / io.Writer 인터페이스를 받는 역할
- fmt : 기본적인 출력과 입력포맷(?) 기능 제공
- log : 여러가지 logger들을 제공하는 패키지
등등등