### 7-3-1. 전위 순회



루트 노드 → 왼쪽 서브 트리 → 오른쪽 서브 트리

![Untitled 3](https://user-images.githubusercontent.com/80656733/152335493-e0a71aa6-b231-4a28-bc28-e3988a2e5dda.png)

```c
//전위 순회 코드
void preorder( char *t, int n, int size ){
	if (n > size || t[n] == 0) return;
	
	printf("%c ", t[n]); //루트 노드
	preorder(t,2*n,size); //왼쪽 서브 트리
	preorder(t,2*n+1,size); //오른쪽 서브 트리
}
```