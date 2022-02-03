### 7-3-3. 후위 순회



왼쪽 서브 트리 → 오른쪽 서브 트리 → 루트 노드

![Untitled 5](https://user-images.githubusercontent.com/80656733/152335502-ec0b3e50-c80a-4c44-9baf-1808e209101f.png)

```c
//후위 순회 코드
void postorder( char *t, int n, int size ){
	if (n > size || t[n] == 0) return;
	
	postorder(t, 2*n, size); //왼쪽 서브 트리
	postorder(t, 2*n+1, size); //오른쪽 서브 트리
	printf("%c ", t[n]); //루트 노드
}
```