# while 반복문 질문 반복

while 반복문으로 계산기 만들기 작업을 하다가 while 문법의 반복되는 구조를 모르고 사용하여 간단한 문제임에도 시간이 오래걸려서 기록해둔다.

### 초기 코드

```py
playing = True
  a = int(input("Choose a number:\n"))
  b = int(input("Choose another one:\n"))
  operation = input(
    "Choose an operation:\n    Options are: + , - , * or /.\n    Write 'exit' to finish.\n"
    )

while playing:
   if operation == "+":
        print(a + b)
    elif operation == "-":
        print(a - b)
    elif operation == "*":
        print(a * b)
    elif operation == "/":
        print(a / b)
    elif operation == "exit":
        break
    else:
        print("알 수 없는 연산자입니다.")
```

보통 while 반복문은 while 다음의 조건이 True 이면 아랫줄로 내려가서 명령을 실행하고, 다시 윗줄로 돌아간다.

그런데 맨 처음 내 초기 코드를 보면 input 함수를 가진 변수 a,b 가 while 반복문 밖에 있었기 때문에 a+b,a-b 등등 계산된 값만 반복됐다.

### 변경된 코드

```py

playing = True

while playing:
    a = int(input("Choose a number:\n"))
    b = int(input("Choose another one:\n"))
    operation = input(
        "Choose an operation:\n    Options are: + , - , * or /.\n    Write 'exit' to finish.\n"
    )

    if operation == "+":
        print(a + b)
    elif operation == "-":
        print(a - b)
    elif operation == "*":
        print(a * b)
    elif operation == "/":
        print(a / b)
    elif operation == "exit":
        break
    else:
        print("알 수 없는 연산자입니다.")
```

그래서 위와 같이 변수 a,b,operation 을 while 반복문 안으로 들여온 결과 질문 --> 답, 질문 --> 답 순으로 결과를 얻을 수 있게됐다.
