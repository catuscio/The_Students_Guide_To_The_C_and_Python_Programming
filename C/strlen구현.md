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
	int i = 0;			//str을 탐색할 인덱스 인자 i 선언
	while (str[i])			//str[i]가 null이 되기 전까지 반복
		i++;			//null이 아니면 i에 1씩 누적
	return i;			//i값(==문자열의 길이) 반환
}
```
