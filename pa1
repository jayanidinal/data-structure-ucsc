#include<stdlib.h>
#include<stdio.h>
#include<stdbool.h>

#define MAX_SIZE 100

void printSet(int B[], int n) {
	bool b = false;
	printf("{");
	for (int i = 1; i <= n; i++) {
		if (B[i] == 1) {
			printf("%d", i);
			b = false;
			for (int j = i + 1; j <= n; j++) {
				if (B[j] == 1) {
					b = true;
					break;
				} 
			}
			if (b) {
				printf(", ");
			}
		}
	}
		printf("}\n");
}

void printSubsets(int B[], int n, int k, int i) {
	if (k == 0) {
		printSet(B, n);
	}
	else if (k > n - i + 1) {
		return 0;
	}
	else {
		B[i] = 1;
		printSubsets(B, n, k - 1, i + 1);
		B[i] = 0;
		printSubsets(B, n, k, i + 1);
	}
}

int main(int argc, char* argv[]) {
	int B[MAX_SIZE + 1];
	int i = 1;
	int n ;
	int k ;
	char c;
	int pd1 = sscanf(argv[1], "%d%c", &n, &c);
	int pd2 = sscanf(argv[2], "%d%c", &k, &c);

	if (k < 0 || k > n || n > 100) {
		printf("Usage: Subset n k (n and k are ints satisfying 0<=k<=n<=100)\n");
		return EXIT_FAILURE;
	}
	
	if (argc != 3) {
		printf("Usage: Subset n k (n and k are ints satisfying 0<=k<=n<=100)\n");
		return EXIT_FAILURE;
	}

	if(pd1 != 1 || pd2 != 1){
			printf("Usage: Subset n k (n and k are ints satisfying 0<=k<=n<=100)\n");
			return EXIT_FAILURE;
	}

	for (int j = 0; j < MAX_SIZE + 1; j++) {
		B[j] = 0;
	}

	printSubset(B, n, k, i);
	return EXIT_SUCCESS;

}
