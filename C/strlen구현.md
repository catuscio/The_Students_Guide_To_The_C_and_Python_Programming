# strlen()
- `<string.h>`에서 문자열의 길이를 구하는 함수

## 구현
```c
int len(char* str) {			    //문자열의 길이를 구하는 함수 len() 선언
	for (char* p = str;; p++)	  //포인터 변수 p로 문자열 탐색
		if (*p == '\0')			      //포인터값이 null이면
			return (p - str);			  //연산 종료 후 str의 길이 반환
}
```
