# Hangman-proj
Project Source Code:
```
#include<iostream.h>
#include<conio.h>
#include<string.h>
#include<dos.h>
#include<graphics.h>
#include<process.h>
#include<stdio.h>
#include<fstream.h>
```
char fname[20],lname[20];int age;long phno;
char a[10];
int noletter;
int correct=0;
int score=0;
int wro=0;//no of wrong inputs
class hman
{public:
	void dispd();
void cover();
void player();
void q1();
void q2();
void q3();
	void q4();
void instructions();
void loading();
void wordfunc(char[]);
void stand(int);
}obj;
void hman::cover()
{clrscr();
int gdriver=DETECT,gmode;
initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
settextstyle(7,0,7);
outtextxy(50,10,"H A N G M A N ");
settextstyle(1,0,3);
outtextxy(300,425,"Press enter to continue");
line(170,150,300,150);
line(170,150,170,300);
rectangle(120,300,230,370);
line(170,150,300,150);
line(170,150,170,300);
rectangle(120,300,230,370);
line(300,150,300,175);
circle(300,200,25);
circle(290,190,3);
circle(310,190,3);
line(290,205,310,212);
line(300,225,300,350);
line(300,240,260,270);
line(300,240,340,270);
line(300,350,260,385);
line(300,350,340,385);
getch();
}
void hman::instructions()
	{
	clrscr();
	int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
	int x=getmaxx();
	int y=getmaxy();
	settextstyle(6,0,3);
	outtextxy(0,0,"WELCOME TO HANGMAN!!!!!");
	cout<<"\n\nInstructions:\n";
	cout<<"1)The word to guess is represented by a row of dashes.\n2)A clue has been given to help you guess the word\n3)Every time you guess a letter the hangman will be displayed with its elements\n4)For every right word you get 10 points.\n";
	settextstyle(1,0,3);
	outtextxy(200,200,"GOOD LUCK!!!!!");
	getch();
	}
void hman::loading()
	{clrscr();
	int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
settextstyle(4,0,4);
outtextxy(240,125,"LOADING");
for(int i=0;i<getmaxx();i++)
{delay(10);
circle(i,200,20);}
getch();
}
void hman::wordfunc(char a[])
{       correct=0;
	wro=0;
   clrscr();
   int gdriver=DETECT,gmode;
   initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
   char c;
   int count=0;
   char ex;
   int i;
   int k=0;
   char b[]="_____________";
   do
     {
	cout<<"\n";
	cout<<"/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\ \n\n\n";
	cout<<"Please enter letter or number.\n";
	cin>>c;
	getch();
	for(i=0;a[i]!='\0';i++)
		{  k=0;
		   if(c==a[i])
			{

				  k=1;
			}

			  if(k==1)
			  break;

		}
   if(k!=1)
   wro=wro+1;

   if(wro==6)
  { cout<<"YOU LOSE THIS ROUND...BETTER LUCK NEXT TIME...:(\n";
    cout<<"The answer is:"<<a<<endl;
   break;
   }
   stand(wro);
   count=strlen(a)-i-1;
   if(k==1)
      {
	b[i]=c;
	correct++;
      }
  if(c==a[0])
  b[0]=c;

  cout<<"your word-\n";
  for(i=0;i<(strlen(a));i++)
  cout<<b[i]<<"   ";

   if(correct==noletter)
  {
  score=score+10;
  cout<<"YOU WIN THIS ROUND!! \n YOUR CURRENT SCORE IS: "<<score<<"\n";
  wro=0;
  break;
  }
  cout<<"\n\nPress (.) to go to exit.\n\nIf you want to continue,press any other key.\n\n";
  cin>>ex;
  if(ex=='.')
  dispd();
  cout<<"\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\\/\ \n";
  }while(ex!='.');
  getch();
  }
void hman::stand(int wrongs)
	{
	int gdriver=DETECT,gmode;
	int x,y,i;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
	x=getmaxx()/2;
	y=getmaxy()/2;
	cout<<"YOUR CURRENT HANGMAN:\n";
	rectangle(x,y,100,200);
	line(200,50,200,200);
	line(200,50,400,50);
	line(400,50,400,75);
	switch(wrongs)
	{
	case 1:
	circle(400,95,20);
	break;
	case 2:
	circle(400,95,20);
	line(400,115,400,205);
	 break;
	case 3:
	circle(400,95,20);
	line(400,115,400,205);
	line(400,150,350,115);
	break;
	case 4:
	circle(400,95,20);
	line(400,115,400,205);
	line(400,150,350,115);
	line(400,150,450,115);
         break;
	case 5:
	circle(400,95,20);
	line(400,115,400,205);
	line(400,150,350,115);
	line(400,150,450,115);
	line(400,205,350,240);
	break;
	case 6:
	circle(400,95,20);
	line(400,115,400,205);
	line(400,150,350,115);
	line(400,150,450,115);
	line(400,205,350,240);
	line(400,205,450,240);
	outtextxy(400,400,"You Lose!!!!! :(");
	break;
	}
getch();
	closegraph();
	}
void hman::q1()
{clrscr();
int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
cout<<"guess the country from its flag..\n";
	setfillstyle(1,17);
	rectangle(50,80,100,150);
	floodfill(90,90,15);
	setfillstyle(1,15);
	rectangle(100,150,75,80);
	floodfill(90,90,15);
	setfillstyle(1,4);
	rectangle(75,80,125,150);
	floodfill(105,105,15);
getch();
noletter=6;
wordfunc("france");
}


void hman::q2()
{clrscr();
int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
cout<<"world no smoking day is on oct _____\n";
	setfillstyle(1,15);
	rectangle(110,140,220,160);
	floodfill(150,150,15);
	setfillstyle(1,14);
	rectangle(95,140,150,160);
	floodfill(97,145,15);
	setcolor(4);
	line(80,110,220,180);
	line(200,110,80,180);
getch();
	noletter=6;
	wordfunc("fourth");
	}
void hman::q3()
{  clrscr();
	int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
	cout<<"When was the first camera patented( the year)?\n";
	rectangle(100,100,350,250);
	circle(275,175,50);
	circle(275,175,25);
	rectangle(300,90,350,100);
	rectangle(120,150,200,180);
	getch();
	noletter=4;
	wordfunc("1863");}
void hman::q4()
	{clrscr();
	int gdriver=DETECT,gmode;
	initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
cout<<"Which American proffessional bowler has amassed records of 41 titles and 6 bowler-of-the-year awards\n on the Proffessional Bowler's Association Tour? Give his first name.\n";
	circle(200,200,100);
	circle(250,150,10);
	circle(275,190,10);
	circle(230,190,10);
	getch();
	noletter=4;
	wordfunc("earl");
}

void hman::player()
	{clrscr();
	fstream fo;
	fo.open("rec.dat",ios::out|ios::binary);
cout<<"Enter the details to be stored:"<<endl;
	cout<<"Enter first name:"<<endl;
	gets(fname);
	fo<<fname;
	cout<<"Enter last name:"<<endl;
	gets(lname);
	fo<<lname;
	cout<<"Enter age:"<<endl;
	cin>>age;
	fo<<age;
	cout<<"Enter phone no:"<<endl;
	cin>>phno;
	fo<<phno;
	fo.close();
}
void hman::dispd()
	{fstream fo;
	fo.open("rec.dat",ios::in|ios::binary);
	fo>>score;
	cout<<"The details of the player are:\n";
	fo>>age;
	cout<<"Age:\t"<<age<<"\n";
	fo>>phno;
	cout<<"Phone number:\t"<<phno<<"\n";
	fo>>score;
	cout<<"Score:\t"<<score<<"\n";
	fo.close();
getch();
	exit(0);}
void main()
	{ obj.cover();
	obj.instructions();
	obj.loading();
	obj.player();
	obj.q1();
       	obj.q2();
obj.q3();
	obj.q4();
	obj.dispd();
getch();
}





