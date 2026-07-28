---
title: "VS Code Code Runner 설치 및 C언어 실행 방법"
date: 2026-07-28 08:29:00 +0900
categories: [공부, 개발환경]
tags: ["CodeRunner", "VSCode", "C언어", "코드실행", "정보처리기사"]
description: "VS Code에서 Code Runner 확장 프로그램을 설치하면 터미널 명령어 없이 버튼 하나로 C언어 코드를 바로 실행할 수 있어요."
series: "정보처리기사 공부일지"
---

C언어 환경 설정까지 끝났다면 이제 코드를 편하게 실행할 수 있는 **Code Runner** 를 설치해봐요. 터미널에서 `gcc` 명령어 매번 치지 않아도 버튼 하나로 바로 실행돼요.

## Code Runner 설치

1. VS Code 실행
2. 왼쪽 사이드바에서 **Extensions** 아이콘 클릭 (또는 `Ctrl + Shift + X`)
3. 검색창에 **Code Runner** 입력
4. **Code Runner** (작성자: Jun Han) 선택 후 **Install** 클릭

## 실행 방법

설치 후 C언어 파일(`.c`)을 열고 오른쪽 상단의 **▶ 버튼** 클릭하거나 `Ctrl + Alt + N` 단축키를 누르면 바로 실행돼요.

실행 결과는 하단 **OUTPUT** 탭에서 확인할 수 있어요.

## 한 가지 설정 추가 (중요)

기본 상태에서는 터미널이 아닌 OUTPUT 탭에서 실행돼서 **사용자 입력(scanf 등)이 안 돼요.** 아래 설정을 바꿔줘야 해요.

1. `Ctrl + ,` 로 설정 열기
2. 검색창에 **code-runner.runInTerminal** 입력
3. 체크박스 **활성화**

이 설정을 켜야 터미널에서 실행되면서 `scanf` 같은 입력 함수도 정상 작동해요.

## 테스트

아래 코드로 잘 되는지 확인해봐요.

```c
#include <stdio.h>

int main() {
    int a, b;
    printf("두 숫자를 입력하세요: ");
    scanf("%d %d", &a, &b);
    printf("합계: %d\n", a + b);
    return 0;
}
```

`Ctrl + Alt + N` 으로 실행 후 숫자 두 개 입력했을 때 합계가 나오면 완료예요.
