# strlen()
- `<string.h>`에서 문자열의 길이를 구하는 함수

## 구현(1) - for문
```c
int len(char* str) {			    	//문자열의 길이를 구하는 함수 len() 선언
	for (char* p = str;; p++)	  	//포인터 변수 p로 문자열 탐색
		if (*p == '\0')			//포인터값이 null이면
			return (p - str);	//연산 종료 후 str의 길이 반환
}
```

## 구현(2) - while문
```c
int len(char* str) {
	char* p = str;		//문자열 탐색할 포인터 변수 p 선언 후 str에 할당
	int cnt = 0;		//문자열의 길이 저장할 변수 cnt 선언
	while (*p)		//*p가 null이 되기 전까지
		cnt++;		//cnt값에 1씩 누적
	return cnt;		//cnt값 반환
}
```
