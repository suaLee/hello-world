# hello-world
//이항계수2
//자연수 N과 정수 K가 주어졌을 때 이항 계수(NK)를 10, 007로 나눈 나머지를 구하는 프로그램을 작성하시오.

#include <stdio.h>

/*int factorial(int N) {
	int N1 = N;
	for (int i = 1; i < N; i++) {//N!
		N1 = N1*(N - i);
	}
	
	return N1;
}*/

int factorial(int N) {
	if (N == 0 || N == 1) {
		return 1;
	}

	return N*factorial(N - 1);
}

int denominator(int N1,int N, int K) {//분모
 //K!(N-K)!
	int N2;
	N2=factorial(K)*factorial(N - K);
	return N2;
}

int binomial_coefficient(int N1, int N2) {
	int binomial = N1 / N2;
	return binomial;
}

int main() {
	int N, K;
	scanf("%d %d", &N, &K);
	int N1 = factorial(N);
	int N2 = denominator(N1, N, K);
	int bino=binomial_coefficient(N1, N2);
	printf("%d", bino % 10007);
	


	return 0;
}
