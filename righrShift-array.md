# righrShift-array
![题干](http://i1.ciimg.com/1949/051772c6d4334c38.png)

```C
/*自己写的没考虑M>N的情况，这个抄的。*/
#include <stdio.h>
int main() {
    int array[101];
    int n, m; 
    int i; 
    scanf("%d %d", &n, &m);
    for (i = 0;i < n;i++) {
        scanf("%d", &array[i]);
    }
    while (m > n) {
        m %= n;
    }
    if (m == 0) {
        for (i = 0;i < n - 1;i++)
            printf("%d ", array[i]);
        	printf("%d\n", array[n - 1]);
    } else {
        for (i = n - m;i < n;i++){
			printf("%d ",array[i]);
		}
        for (i = 0; i < n - m -1; i++){
        	printf("%d ", array[i]);
		}
        printf("%d\n", array[n - m -1]);
    }
    return 0;
}
```