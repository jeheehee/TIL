# Today I Learned

0112
### Git bash
### Visual Studio
### Mark down

0113
### Git & Github
+ clone을 하면 init은 자동으로 된다. 

```
$ git remote add origin https://github.com/jeheehee/TIL.git
$ git clone https://github.com/jeheehee/TIL.git
# 차이점 : init하냐 안하냐

$ git remote -v
```

#### git push

+ push 전에 1) git add . 와 2) git commit -m '<메세지>' 해야함
```
$ git push origin master
```

0114
### 텔레그램 챗봇 만들기
+ VS 터미널에서 python <파일명>.py 실행시 python만 나올때, 시스템 경로를 수정해야 함
+ 파이썬과 pip경로 모두
+ 바로가기 경로는 XX! :)

-----------



0117.mon

### Python 기본
### Gitlab에 숙제 올리기
### Github에 push& pull 연습

0118

### for& while

### 변수 type

- mutable & immutable

0119

### def 정의와 호출

```python
def <함수이름> (<변수>): # 가변인자: *args **kwargs
    return result
```

- 함수의 모습
- return을 사용해서 결과값 반환하기
- 매개변수/ 전달인자에 대해 이해하기
  - 필수인자/ 선택인자
  - 위치인자/ 키워드 인자/ 기본값을 가지는 인자/ 가변인자/ 키워드 가변 인자
- 함수 스코프 이해하기
  - 지역변수/ 전역변수
  - 변수의 사용범위 생명주기
- 이름검색 LEGB
  - global/ nonlocal 키워드



### comprehension (안쓰면 항상 헷갈리는)

+ dict comprehension

0120

### 재귀함수

> 아 이건 연습 필요

0121 : 관통pjt

### Python을 활용한 데이터 수집 I

+ 변수와 key값 이름, type을 정확히 읽어야 함
+ 문제에서 요구하는 사항을 제대로 읽어야 함 
  + 이름 출력하라고 했는데 뭐 다 출력하면서 시간 낭비하지 말기 ㅠ.ㅠ
+ for문 사용시 초기값 설정 위치, 설정값 주의 => 안그러겠지만... 흑흑....
+ 주석 깔끔하게 쓰기~

---------

