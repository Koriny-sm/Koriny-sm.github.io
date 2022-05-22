---
layout : single
title : "C언어"
---

``` # c언어 실습 및 과제

#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#define _CRT_SEQURE_NO_WARNINGS

void print_str(char str[][50], int n)
{
	int i;
	for (i = 0; i < n; i++)
		printf("영단어%d : %s \n", i + 1, str[i]);
}

void str_exchange(char str[][50], int n)
{
	int i, j;
	char temp[50];

	for (i = 0; i < n - 1; i++)
	{
		for (j = i + 1; j < n; j++)
		{
			if (strcmp(str[i], str[j]) > 0)
			{
				strcpy_s(temp, str[i]);
				strcpy_s(str[i], str[j]);
				strcpy_s(str[j], temp);
			}
		}
	}
}
int main()
{
	char str[5][50];
	int i, j;
	int n = 5;

	for (i = 0; i < n; i++)
	{
		printf("영단어 입력 : ");
		scanf_s("%s", str[i], 50);
	}
	printf("\n");

	printf("=====저장된 문자열=====\n");
	print_str(str, n);

	printf("\n");
	str_exchange(str, n);

	for (i = 0; i < n; i++)
		printf("영단어%d : %s \n", i + 1, str[i]);
	return 0;
}
```
