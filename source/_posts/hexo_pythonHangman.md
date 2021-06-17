---
title: Python으로 행맨 게임 만들기
tags: [python]
---

저번에 과제로 나온 행맨 게임 만들기이다.
파이썬에는 랜덤으로 숫자를 만들어주는 함수가 있다고 하는데 나는 만들어 보았다.

random*Word() 에서는 랜덤으로 숫자를 추출해 Word_list을 뽑는다.
그 다음 Word_list에서 랜덤으로 나온 값을 배열 형태로 만들어서 각각 저장을 한다.
그리고 word_qust에는 Word_list의 배열의 개수 만큼 *이 있는 배열을 만들어 주는 것이다.

```python
import random

word_list = []
word_qust = []
word_len = 0
def random_Word() :
    # 글로벌 변수 생성
    global word_list
    global word_qust
    global word_len
    while True :
        list = []  # 리스트생성
        rnum = random.randint(0, 8)

        for i in range(1):
            while rnum in list:
                rnum = random.randint(0, 8)
            list.append(rnum)

        list.sort()

        Word_list = ["apple", "actor", "airplane", "always", "animal", "angry", "arrive", "autumm", "baby", "maplestory"]
        word_len = len(Word_list[list[0]])
        random_word = Word_list[list[0]]

        word_list = []
        word_qust = []

        print("\n")

        # 랜덤으로 뽑힌 단어을 리스트화 시키는 것이다.
        for i in random_word:
            word_list.append(i)

        # 우선 랜덤으로 뽑힌 단어의 글자 수를 받아와 그 겟수 만큼 _을 word_qust에 저장
        for i in range(word_len):
            word_qust.append("_")

        # 리스트가 된 word_qust을 print로 출력 여기서
        # end =" " 는 프린트로 출력 될때 줄바 꿈을 공백으로 변경하는 것이다.
        for i in word_qust:
            print(i, end=" ")
        break
```

try_num는 남은 횟수를 저장하는 변수 이다.

처음에 user_ch에 알파벳을 입력 해주면
for문을 통해 word_list와 비교를 한다.

만약에 사용자가 입력한 값과 word_list와 같다면

```python
def ex():
    try_num = 10
    print("\n")
    print("현제 남은 횟수는 " + str(try_num) + "번 입니다.")

    score = 0
    while True:
        user_ch = input("알파벳을 입력해주세요 > ")
        # 입력 받은 input을 word_list랑 비교 한다.
        for i in word_list:
            # 만약에 사용자가 입력한 값이 word_list에 있는 값과 같으면
            # *로 처리하는 과정을 적은것이다.
            # 이거는 중복되는 글자들을 무시하기 위한것이다.
            if user_ch == i:
                word_qust[word_list.index(i)] = user_ch
                word_list[word_list.index(i)] = "*"
                for k in word_qust:
                    print(k, end=" ")
                print("\n")
                print("정답 입니다.")
                score = score + 1
                try_num = try_num - 1
                print("현제 남은 횟수는 " + str(try_num) + "번 입니다.")
                break
            if user_ch != i:
                print("틀렸습니다.")
                try_num = try_num - 1
                print("현제 남은 횟수는 " + str(try_num) + "번 입니다.")
                break
        # 횟수가 0이 되면 게임이 끝나고 다음 문제가 나온다.
        if try_num == 0 :
            print("아웃 입니다.")
            print("다음 문제 나옵니다.")
            break
        if score == word_len:
            print("정답입니다!")
            break


if __name__ == "__main__":
    while True:
        random_Word()
        ex()
```
