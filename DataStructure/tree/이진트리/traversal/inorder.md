### 7-3-2. 중위 순회



왼쪽 서브 트리 → 루트 노드 → 오른쪽 서브 트리

![Untitled 4](https://user-images.githubusercontent.com/80656733/152335500-12b80bfc-731f-4f62-b10c-a7430eb60f27.png)

```c
//중위 순회 코드
void inorder( char *t, int n, int size ){
	if (n > size || t[n] == 0) return;
	
	inorder(t,2*n,size); //왼쪽 서브 트리
	printf("%c ", t[n]); //루트 노드
	inorder(t, 2*n+1, size); //오른쪽 서브 트리
}
```