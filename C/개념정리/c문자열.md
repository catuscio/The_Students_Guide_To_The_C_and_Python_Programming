# 문자열(string)
- 연속된 문자들의 모임을 문자열이라고 한다.
- 배열과 비슷하게 사용 가능하다.

## 문자 배열의 선언 및 초기화
- 초기값을 지정하는 경우에는 문자 배열의 크기를 생략할 수 있다.
- '문자열의 길이+1'의 크기로 문자 배열을 할당해야 한다.
- 문자 배열 전체를 ""를 이용해 널 문자열로 초기화 가능하다.
```c
char str[] = "abc";
char str[10] = "";
```
- 이때 문자열을 통해 초기화 하는 것은 __문자열의 선언 시에만 가능하다.__\
- 이후에는 `strcpy()`함수를 사용해야 한다.

## 문자 배열 탐색
- for문을 이용해 탐색할 수 있다.
```c
for (int i = 0; i < str[i] != '/0'; i++)    //str의 원소값이 null이 되기 전까지(문자열의 끝까지) 탐색
```

## 표준 C 문자 처리 함수
- `<ctype.h>`를 포함하여 사용할 수 있다.
```
- isalnum(ch);    //알파벳이나 숫자인지 검사(알파벳이거나 숫자이면 1 반환, 아니면 0 반환)
- isdigit(ch);    //숫자인지 검사
- isupper(ch);    //대문자인지 검사
- isxdigit(ch);   //16진수 숫자인지 검사
- isalpha(ch);    //알파벳인지 검사
- islower(ch);    //소문자인지 검사
- isspace(ch);    //공백 문자인지 검사
- toupper(ch);    //대문자로 변환
- tolower(ch);    //소문자로 변환
```
> 예시
```c
#include <stdio.h>
#include <ctype.h>

int main() {
	char str[200];

	gets(str);

	for (int i = 0; str[i]; i++) {
		if (isspace(str[i])) {
			printf("여기 띄어쓰기 있음\n\n");
		}
		if (isdigit(str[i])) {
			printf("%c\n", str[i]);
			printf("이거 숫자임\n");
		}
		if (isalpha(str[i])) {
			printf("%c\n", str[i]);
			printf("이거 알파벳임 그리고 ");
		}
		if (isupper(str[i])) {
			printf("대문자임\n");
		}
		if (islower(str[i])) {
			printf("소문자임\n");
		}
	}
}
```
> 입력 `Hi Hello 10`
```c
H
이거 알파벳임 그리고 대문자임
i
이거 알파벳임 그리고 소문자임
여기 띄어쓰기 있음

H
이거 알파벳임 그리고 대문자임
e
이거 알파벳임 그리고 소문자임
l
이거 알파벳임 그리고 소문자임
l
이거 알파벳임 그리고 소문자임
o
이거 알파벳임 그리고 소문자임
여기 띄어쓰기 있음

1
이거 숫자임
0
이거 숫자임
```

## 표준 C 문자열 처리 함수
- `<string.h>`를 포함하여 사용할 수 있다.
```
- strlen(str);          //str의 길이를 구한다(null 문자 제외)
- strcpy(dest, src);    //src를 dest로 복사한다.
- strcmp(lhs, rhs);     //lhs와 rhs를 비교해서 같으면 0, lhs>rhs면 양수, lhs<rhs면 음수 반환
- strcat(dest, src);    //dest의 끝에 src를 연결한다.
- strchr(str, ch);      //str에서 ch문자를 찾는다. (찾은 문자의 주소 반환)
- strstr(str, substr)   //str에서 substr문자열을 찾는다(찾은 문자열의 주소 반환)
- strtok(str, delim)    //str을 delim을 이용해서 토큰으로 분리한다. (토큰 문자열 반환)
```
### `strncpy(dest, src, size)` 함수 오류 해결법
해당 함수는 dest로 src를 복사하되, size까지 복사한다. 가령, size = 4일 경우, src의 네번째 문자까지만 복사한다.\
strncpy를 통해 복사된 dest에 쓰레기값이 검출될 경우,
```c
dest[size] = '\0';
```
위의 코드처럼 dest의 끝을 강제로 매겨 해결할 수 있다.
