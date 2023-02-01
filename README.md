# wedding
# c
내 결혼식에 내친구와 내친구의 친구까지만을 참석하기로 했다. 나의 동기의 수는 n개로 첫째줄에 입력하고 둘째줄에 m개를 입력해서 m개의 줄에 친구관계를 입력하자. 1은 나 이고 예를 들어 1 2, 2 3 이면 2는 내친구 3은 내친구의 친구가 된다. 결혼식참석 가능한 수를 구하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int a[100]={0},b[100]={0}; //내풀이 
 
int check(int a[],int b[],int i){
	int cnt[100],bad[100];
	int j=0;
	if(a[i] == 1){
		cnt[j]=b[i];
		return 1;
	}
	while(cnt[j] != 0){
	    if(cnt[j] == a[i] && cnt[j] != b[i]){
		    cnt[i]=b[i];
		    if(bad[j] != a[i]){
		    	return 2;
			}
		}
	    j++;
	}
	return 0;
}


int main(){
	int n,m,i,a[100]={0},b[100]={0},count=0;
	scanf("%d",&n);
	scanf("%d",&m);
	for(i=0;i<m;i++){
		scanf("%d %d",&a[i],&b[i]);}
	for(i=0;i<m;i++){
		check(a,b,i);
		if(check(a,b,i)==1){
			count++;}
		if(check(a,b,i)==2){
			count++;}}
	printf("총 하객수: %d",count);
	return 0;
}
