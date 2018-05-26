#include<stdio.h>

void detab();
void strdetab(char* str);

int main() {

	detab();


	char str[] = "123\t1234\t23\t1223243243434\t123\n";
	strdetab(str);

	return 0;
}

void detab() {
	char c;
	int n = 0;
	while ((c = getchar()) != EOF) {
		if (c != '\t') {
			putchar(c);
			n++;
		}
		else {
			for (int i = 0; i < 8 - n % 8; i++) {
				putchar(' ');
			}
			n = 0;
		}
	}
}

void strdetab(char* s) {
	int i = 0;
	int n = 0;
	while (s[i] != '\0') {
		if (s[i] != '\t') {
			putchar(s[i]);
			n++;
		}
		else {
			for (int j = 0; j < 8 - n % 8; j++) {
				putchar(' ');
			}
			n = 0;
		}
		i++;
	}
}
