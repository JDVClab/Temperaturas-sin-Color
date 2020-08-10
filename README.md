# Temperaturas-sin-Color
Sin color
using namespace std;
#include <iostream>
#include <conio.h>
#include <stdio.h> 
#include <stdlib.h> 
#define WEEK 7*1 
void shellSort(double week_temp[])
{
	system("color 0a");
	const int week_array = WEEK;
	int counter, steps, claw,i;
		for(counter = WEEK/2; counter != 0; counter /=2)
			for(steps = 1; steps != 0;)
			{
				steps=0;
				for(i=counter; i < WEEK; i++)
					if(week_temp[i - counter] > week_temp[i])
					{
						claw = week_temp[i];
						week_temp[i] = week_temp[i - counter];
						week_temp[i - counter] = claw;
						steps ++;
					}
			}
	cout<<"\n Los valores ordenados de forma ascendente son";
		for(int i = 0; i < week_array; i++)
			cout<<week_temp[i]<<"  C ";
	cout<<"\n Los valores ordenados de forma descendente son";
		for(int j = week_array-1 ; j >= 0; j--)
			cout<<week_temp[j]<<"  C ";		
};
void printHotCold(string HotDay, string ColdDay)
{
	cout<<"\n El dia mas frio fue el: "<<ColdDay<<"\n El dia mas caluroso fue el: "<<HotDay<<endl;
}
void getHotCold_Day(double dWeek[], int size, string week[])
{
	string Hot_Day, Cold_Day;
	double Max_temp = 0, Min_temp = 999;
	for(int i = 0; i < size ; i++)
	{
		if(Max_temp < dWeek[i])
		{
			Max_temp = dWeek[i];
			Hot_Day = week[i]; 	
		}	
		if(Min_temp > dWeek[i])
		{
			Min_temp = dWeek[i];
			Cold_Day = week[i];
		}	
	}
	printHotCold(Hot_Day,Cold_Day);	
}
void get_WeekTemp()
{
	string dweek [7] = {"LUNES","MARTES","MIERCOLES","JUEVES","VIERNES","SABADO","DOMINGO"};
	double dayTemp [WEEK];
	for(int i = 0; i < WEEK ; i++)
	{
		cout<<"Capture la temperatura promedio del dia "<<dweek[i]<<": ";
		cin>> dayTemp[i];	
	}
	shellSort(dayTemp);
	getHotCold_Day(dayTemp, WEEK, dweek);		
};
int main()
{
	get_WeekTemp();
	return 0;
}
