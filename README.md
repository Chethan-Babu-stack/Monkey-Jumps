//# Monkey-Jumps
//A Monkey can Jump one step initially . At n th step it can jump either n steps or n-1 steps or n+1 steps. Then find the number //of jumps that a monkey will make at each step to move to destination step.



//program:
#include<stdio.h>

int path(int nthStep,int sum,int nextStep)
{
	int check=-1;

	sum=sum+nextStep;

	if(sum == nthStep)
	{
		printf("%d ",nextStep);
		return 0;
	}

	if(sum > nthStep)
	{
		return -1;
	}

	if(check == -1)
	{
		if(sum+nextStep+1 <= nthStep)
		{
			if((check = path(nthStep,sum,nextStep+1)) == 0)
			{
				printf("%d ",nextStep);
				return 0;
			}
	
		}
	}

	if(check == -1)
	{
		if(sum+nextStep <= nthStep)
		{
			if((check = path(nthStep,sum,nextStep)) == 0)
			{
				printf("%d ",nextStep);
				return 0;
			}
	
		} 
	}

	if(check == -1)
	{
		if(sum+nextStep-1 <= nthStep)
		{
			if((check = path(nthStep,sum,nextStep-1))==0)
			{
				printf("%d ",nextStep);
				return 0;
			}
		}	
	}
	return -1;

}
int main()
{
	int n;
	printf("Enter Step\n");
	scanf("%d",&n);
	if(path(n,0,1)==0)
		printf("path found\n");
	return 0;
}
