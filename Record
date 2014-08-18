/*
Tiltle: Pogram Appropriate For Business
Author: Jerald Limqueco and Janela Angeles
Brief Description:
     This program saves your employees name, age and salary. It also records your stock, and allows you to edit, delete, and dsplay whatever data inputted.
Main learnings: 
     We learned about new functions, and other things that we need in programming using C language. Some of these are the ctype.h, string.h, conio.h, and gotoxy.
     We also had to manage our time properly, so that we will be able to finish the project on time.
     Another thing we had to adjust to is dividing the work according to our capabilities, since not both of us have the same level of programming skills.
*/

#include<stdio.h>
#include<stdlib.h>
#include<math.h>
#include<conio.h>
#include<windows.h> //we only use this so we can use exit(0)
#include<string.h> //library so we can use some string functions
#include<ctype.h> //declares several functions useful for testing and mapping characters
#include<time.h> //declares time and date structure

#define ANS 15
#define ACS 4

/*mainmenu*/
void StockRecord();
void EmployeesRecord();

/*employees record menu*/
void addemployee();
void displayemployee();
void editemployee();
void deleteemployee();
void mainmenu_2();  

/*structure declaration*/
typedef struct
{
char name[ANS],code[ACS];
float rate;
int quantity;
}rec;
rec item;

/*declaration of display functions*/
void curser(int);
void mainmenu();
void display(rec *,int,int);
void window(int,int,int,int);
void dis_con();
void d_search();
void highlight(int,int);

/*declaration of main menu functions*/
void edit();
void add();
void del();
void exit();

/*declaration of display submenu functions*/
void d_code();
void d_rate();
void d_quan();
void d_all();

/*declaration of checking functions*/
void c_code(char[]);



COORD coord={0,0};                  // this is global variable
                                    //center of axis is set to the top left corner of the screen
void gotoxy(int x,int y)			//gotoxy places cursor at a desired location on screen
{
    coord.X=x;
    coord.Y=y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),coord);
}


FILE *fp, *ft; 
char another, choice;    

//can be used to define class types
struct emp 
    {
        char name[40]; 
        int age; 
        float bs; 
    };

struct emp e; 
char empname[40];
long int recsize; 

int check(char[]);


int main()
{
    char select;    
    
    
    
    while(1)
            {
            //system("cls") is used for clearing the screen	
              system("cls");
			  			  			  
              gotoxy(30,10);
			  printf("\n                                 Main Menu                                   ");
              gotoxy(30,12);
			  printf("\n\n                              A - Stock Record  ");
              gotoxy(30,14);
			  printf("\n\n                              B - Employees Record   ");
              gotoxy(30,16);
			  printf("\n\n                              C - Exit  ");
              gotoxy(30,18);
			  printf("\n\n                              Enter selection: ");
            
            
              scanf("%c",&select);
			 
     
     switch(select)
      {
       case 'A':
       case 'a':
       			 
                 StockRecord();
                 break; 

       case 'B': 
       case 'b': 
       			
                EmployeesRecord();
                 break; 

       case 'C':  
       case 'c': 
       			
                break;
 
                        
      default: 
         printf("\n\n\n Invalid selection");
         return main();            
    } 
 
    getchar(); 

    printf("\n");

    
    if (select == 'C' || select == 'c')
       break; 
    } 
    printf("\n\n Closing...\n");
    exit(0);   
}



// Stock Record
void StockRecord()
{ 	
 mainmenu();
}



void mainmenu()
{
 int i;
 
 const char 
 *menu[]={"   ","   ","   ","   ", "  ","   ", "   "};
 
 system("cls");

 
 gotoxy(33,18);
 printf("Stock Record");
 for (i=0;i<=6;i++)
 {
  gotoxy(30,22+i+1);
  printf("%s\n\n\n",menu[i]);
  }
  curser(7);
 }


void d_search()
{
 
 int i;
    const char *menu[]={"   By Code","   By Rate","   By Quantity","   Back to main menu"};
 system("cls");

 
 gotoxy(33,18);
 printf("SEARCH MENU");
 for (i=0;i<=3;i++)
 {
 gotoxy(30,22+i+1);
 printf("%s\n\n\n",menu[i]);
 }
 curser(4);
}


/*function for cursor movement*/
void curser(int no)
{
    int count=1;
    char ch='0';
    gotoxy(30,23);
 while(1)
 {
  switch(ch)
  {
   case 80:
    count++;
    if (count==no+1) count=1;
    break;
   case 72:
    count--;
    if(count==0) count=no;
    break;
  }
  highlight(no,count);
  ch=getch();
  if(ch=='\r')
  {
   if(no==7)
   {
    if (count==1) add() ;
    else if(count==2) edit();
    else if(count==3) d_all();
    else if (count==4) d_search();
    else if (count==5) del();
    else if (count==6) main();
    else  exit(0);
   }
   if(no==4)
   {
    if (count==1) d_code();
    else if (count==2)d_rate();
    else if (count==3) d_quan();
    else mainmenu();
   }
  }
 }
}


//this is to highlight the phrase where the cursor is pointed
void highlight(int no,int count)
{
 if (no==4)
 {
  
  gotoxy(30,23);
  printf("   By Code          ");
  
  gotoxy(30,24);
  printf("   By Rate          ");
  
  gotoxy(30,25);
  printf("   By Quantity      ");
  
  gotoxy(30,26);
  printf("   Back to main menu");
  
  switch (count)
  {
   case 1:
    gotoxy(30,23);
    printf(" - By Code          ");
    break;
   case 2:
    gotoxy(30,24);
    printf(" - By Rate          ");
    break;
   case 3:
    gotoxy(30,25);
    printf(" - By Quantity      ");
    break;
   case 4:
    gotoxy(30,26);
    printf(" - Back to main menu");
    break;
  }
 }

 if(no==7)
 {

  
  gotoxy (30,24);printf("   Add Stocks      ");
  gotoxy (30,25);printf("   Edit Stocks     ");
  gotoxy (30,26);printf("   Display Stocks    ");
  gotoxy (30,27);printf("   Search Stocks        ");
  gotoxy (30,28);printf("   Delete Stocks   ");
  gotoxy (30,29);printf("   Back to Main Menu    ");
  gotoxy (30,30);printf("   Exit    ");
  
  switch(count)
  {
   
   case 1:
    gotoxy (30,24);
    printf(" - Add Stocks      ");
    break;
   case 2:
    gotoxy (30,25);
    printf(" - Edit Stocks     ");
    break;
   case 3:
    gotoxy (30,26);
    printf(" - Display Stocks    ");
    break;
   case 4:
    gotoxy (30,27);
    printf(" - Search Stocks         ");
    break;
   case 5:
    gotoxy (30,28);
    printf(" - Delete Stocks   ");
    break;
   case 6:
    gotoxy (30,29);
    printf(" - Back to Main Menu          ");
	break;
   case 7:
    gotoxy (30,30);
    printf(" - Exit         ");
    break;
  }
 }
}



/*function to add records*/
void add ()
{
 FILE *file;
 char y[ACS];
 system("cls");

 gotoxy(25,25);
 printf("Enter new record(Y/N)?");
 
 while(toupper(getche())=='Y'){
  system("cls");
  file=fopen("record.txt","ab"); //this is for opening a file where you record your data
  c_code(y);
  strcpy(item.code,y);
  
  gotoxy(22,28);
  printf("Enter rate of the item:");
  scanf("%f",&item.rate);
  
  gotoxy(22,30);
  printf("Enter quantity of the item:");
  scanf("%d",&item.quantity);
  
  gotoxy(22,32);
  printf("Enter name of the item:");
  scanf("%s",item.name);
  
  fseek(file,0,SEEK_END);               //sets the file position of the stream to the given offset
  fwrite(&item,sizeof(item),1,file);   //writes data from the array pointed to by ptr to the given stream
  fclose(file);                       //for closing the recording file
  gotoxy(22,34);printf("Enter new record(Y/N)?");

   }
   mainmenu();
}

 /*function to check availability of code*/
void c_code(char y[])
{
 int flag;
 FILE *file;
 file=fopen("record.txt","rb");
 
 while(1)
 {
  system("cls");
  
  
  gotoxy(32,18);
  printf(" ADD STOCK ")  ;
  
  flag = 1;
  rewind(file);
  gotoxy(22,25);
  printf("Enter new code of the stock:");
  
  scanf(" %[^\n]",y);
  
  while(fread(&item,sizeof(item),1,file)==1)
  {
   if (strcmp(y,item.code)==0)
   {
    flag=0;
    
	gotoxy(26,30);
	printf("Code already exists");
    
	gotoxy(29,32);
	printf("ENTER AGAIN");
	getch();
    
	break;
   }
  }
  if (flag==1)
  break;
 }
}

/*function for editing*/
void edit()
{
 int flag=0,choice;
 char x[ACS],y[ACS];
 FILE *file;
 int size;
 system("cls");
 
 gotoxy(35,18);
 printf("EDIT STOCKS");
 
 gotoxy(25,23);
 printf("Enter item code: ");
 
 scanf("%s",x);
 flag=check(x);
 
 if(flag==0)
 {
  file=fopen("record.txt","r+b");
  rewind(file);
  
  while (fread(&item,sizeof (item),1,file))
  {
   if(strcmp(item.code,x)==0)
   {
    //textcolor(0);
    gotoxy(25,27);
	printf("Name       = %s",item.name);
    
	gotoxy(25,28);
	printf("Code       = %s",item.code);
    
	gotoxy(25,29);
	printf("Rate       = %g",item.rate);
    
	gotoxy(25,30);
	printf("Quantity   = %d",item.quantity);
    
	gotoxy(25,32);
	printf("Do you want to edit this record(y/n):");
    fflush(file);
    
	if(toupper(getche())=='Y')
	{
     //textcolor(0);
     gotoxy(25,34); 
	 printf("1- Edit name ");
     
	 gotoxy(25,35); 
	 printf("2- Edit code ");
     
	 gotoxy(25,36); 
	 printf("3- Edit rate ");
     
	 gotoxy(25,37); 
	 printf("4- Edit quantity ");
     
	 gotoxy(25,39);
	 printf(" Enter your choice(1, 2, 3, 4) ");
     
	 scanf("%d",&choice);
     
	 switch(choice)
	 {
      
	  case 1:
       		system("cls");
       		
       		gotoxy(35,18);
			printf("EDIT STOCKS");
       		
			gotoxy(25,24); 
			printf(" enter new name: ");
       		
			scanf("%s",item.name);
       		
			size=sizeof(item);
       		fseek(file,-size,SEEK_CUR);
			   fwrite(&item,sizeof(item),1,file);
       		break;
      
	  case 2:
       		system("cls");
       
       		gotoxy(35,18);
			printf("EDIT STOCKS");
       		
			gotoxy(25,24);
       		c_code(y);
       		strcpy(item.code,y);
       		size=sizeof(item);
       		fseek(file,-size,SEEK_CUR);
			   fwrite(&item,sizeof(item),1,file);
      		break;
      
	  
	  case 3:
       		system("cls");
       
       		gotoxy(35,18);
			printf("EDIT STOCKS");
       		
			gotoxy(25,24);
       		printf(" enter new rate: ");
       		scanf("%f",&item.rate);
       		size=sizeof(item);
       		fseek(file,-size,SEEK_CUR);
			   fwrite(&item,sizeof(item),1,file);
       		break;
      
	  case 4:
       		system("cls");
       
       		gotoxy(35,18);
	   		printf("EDIT STOCKS");
      
	   		gotoxy(25,24);
       		printf(" enter new quantity: ");
       		scanf("%d",&item.quantity);
       		
			size=sizeof(item);
       		fseek(file,-size,1);
	   		fwrite(&item,sizeof(item),1,file);
       		break;
     }
     gotoxy(27,30);
	 printf("--- item edited---");
     break;
    }
   }
  }
 }
 if (flag==1)
 {
  
  gotoxy(32,30);
  printf("item does not exist");
  
  gotoxy(36,32);
  printf("TRY AGAIN");
 }
 getch();
 fclose(file);
 mainmenu();
}

/*function to display all records*/
void d_all()
{
 int i,j=1;
 FILE *file;
 dis_con();
 file=fopen("record.txt","rb");
 rewind(file);
 i=26;
 fflush(file);
 while(fread(&item,sizeof(item),1,file))
 {
  display(&item,i,j);
  i++;
  j++;
  if ((j%20)==0)
  {
         gotoxy(27,47);/*textcolor(0)*/;
		 printf("press any key to see more...........");
         getch();
         system("cls");
         dis_con();
         i=26;
         continue;
  }
  }
  getch();
  if (i==26) 
  {
  gotoxy(24,30); 
  printf("-- No stocks found --");
 }
 getch();
 fclose(file);
 mainmenu();
}

/*function to display by quantity*/
void d_quan()
{
  int i,j=1;
  int a,b;
  FILE *file;
  dis_con();
  file=fopen("record.txt","rb");
  rewind(file);
  i=26;
  gotoxy(16,20);
  printf("enter lower range: ");
  scanf("%d",&a);
  gotoxy(16,21);
  printf("enter upper range:");
  scanf("%d",&b);
  
  fflush(file);
  while(fread(&item,sizeof(item),1,file))
  {
  if((item.quantity>=a)&&(item.quantity<=b))
  {
   display(&item,i,j);
   i++;
   j++;
   if ((j%20)==0)
   {
    gotoxy(27,47);
	printf("press any key to see more...........");
    getch();
    system("cls");
    dis_con();
    i=26;
    continue;
   }
     }
  }
  getch();
  if (i==26)
  {
  gotoxy(28,30); 
  printf(" no item found ");
 }
 getch();
 d_search();
 fclose(file);
}

/*function to display by rate*/
void d_rate()
{
  int i,j=1;
  float a,b;
  FILE *file;
  dis_con();
  file=fopen("record.txt","rb");
  rewind(file);
  i=26;
  gotoxy(16,20);
  printf("enter lower range: ");
  
  scanf("%f",&a);
  
  gotoxy(16,21);
  printf("enter upper range: ");
  
  scanf("%f",&b);
  fflush(file);
 
  while(fread(&item,sizeof(item),1,file))
  {
  if((item.rate>=a)&&(item.rate<=b))
  {
   display(&item,i,j);
   i++;
   j++;
 
   if ((j%20)==0)
   {
    gotoxy(27,47);
	printf("press any key to see more...........");
    getch();
    system("cls");
    dis_con();
    i=26;
    continue;
   }
  }
  }
 
 getch();
 
 if (i==26)
 {
  gotoxy(28,30); 
  printf(" No item found... ");
 }
 getch();
 fclose(file);
 d_search();
}

/*function to display by code*/
void d_code()
{
  int i,j=1;
  char x[4]={0};
  FILE *file;
  dis_con();
  file=fopen("record.txt","rb");
  rewind(file);
  i=26;
  gotoxy(16,20);
  printf("enter item code: ");
  
  scanf("%s",x);
  
  fflush(file);
  
  while(fread(&item,sizeof(item),1,file))
  {
  if((strcmp(item.code,x)==0))
  {
   display(&item,i,j);
   i++;
   j++;
   break;
  }
  }
  
  if (i==26)
  {
  gotoxy(28,30); 
  printf("\nNo item found...");
  }
  getch();
  fclose(file);
  d_search();
}

/*function to display window for item display*/

void dis_con()
{
 
 system("cls");

 printf("\n\n");
 gotoxy(30,11);
 printf("Stock Record");
 //textcolor(1);
 gotoxy(32,17);
 printf("RECORDS") ;
 //textcolor(8);
 gotoxy(18,23);
 printf ("SN   Item Name   Item Code      Rate     Quantity");
}



/*function to display in screen*/
void display(rec *item,int i,int j)
{
 gotoxy(16,i);
 printf("%4d",j);
 printf("%9s",item->name);
 printf("%12s",item->code);
 printf("%14.2f",item->rate);
 printf("%11d",item->quantity);
}

/*function to delete records*/
void del()
{
 int flag;
 char x[ANS];
 FILE *file,*file1;
 system("cls");
 
 
 gotoxy(29,18);
 printf("\n----------- Delete Stock -----------");
 
 gotoxy(27,27);
 printf("Enter Stock code: ");
 scanf("%s",x);
 
 flag=check(x);
 if(flag==0)
 {
  file1=fopen("record1.txt","ab");
  file=fopen("record.txt","rb");
  rewind(file);
  while (fread(&item,sizeof (item),1,file))
  {
   if(strcmp(item.code,x)!=0)
    fwrite(&item,sizeof(item),1,file1);
  }
  gotoxy(27,29);
  printf("---Stock Deleted---");
  remove("record.txt");  // this is for deleting something from your record
  rename("record1.txt","record.txt");
 }
 if (flag==1)
 {
  gotoxy(25,29);
  printf("---Stock does not Exist---");
  
  gotoxy(30,31);
  printf("TRY AGAIN");
 }
 fclose(file1);
 fclose(file);
 getch();
 mainmenu();
}

/*function to check validity of code while editing and deleting*/
int check(char x[ANS])
{
 FILE *file;
 int flag=1;
 file=fopen("record.txt","rb");
 rewind(file);
 while (fread(&item,sizeof (item),1,file))
 {
  if(strcmp(item.code,x)==0)
  {
   flag=0;
   break;
  }
 }
 fclose(file);
 return flag;
 }

/*function to display box*/

void window(int a,int b,int c,int d)
{
 int i;
 system("cls");
 gotoxy(20,10);


 printf("\n\n");
 gotoxy(30,11);printf("Stock Record");
 
 for (i=a;i<=b;i++){
        gotoxy(i,17);
		printf("\xcd");
        
		gotoxy(i,19);
		printf("\xcd");
        
		gotoxy(i,c);
		printf("\xcd");
        
		gotoxy(i,d);
		printf("\xcd");
        }

 gotoxy(a,17);
 printf("\xc9");
 
 gotoxy(a,18);
 printf("\xba");
 
 gotoxy(a,19);
 printf("\xc8");
 
 gotoxy(b,17);
 printf("\xbb");
 
 gotoxy(b,18);
 printf("\xba");
 
 gotoxy(b,19);
 printf("\xbc");
 
 for(i=c;i<=d;i++)
 {
  gotoxy(a,i);
  printf("\xba");
  
  gotoxy(b,i);
  printf("\xba");
 }
 gotoxy(a,c);
 printf("\xc9");
 
 gotoxy(a,d);
 printf("\xc8");
 
 gotoxy(b,c);
 printf("\xbb");
 
 gotoxy(b,d);
 printf("\xbc");
 
}









  
//employee 
void EmployeesRecord()
  { 
 printf("\n----------- Employees Record -----------\n")  ;
 mainmenu_2();

}

void mainmenu_2()
{
    
    fp = fopen("EMP.DAT","rb+");
    if(fp == NULL)
    {
        fp = fopen("EMP.DAT","wb+");
        if(fp == NULL)
        {
            printf("Access Denied");
            exit(1);
        }
    }
  

    
recsize = sizeof(e);

  
    while(1)
    {
        system("cls"); 
        gotoxy(30,10); 
        printf("1. Add New Record");
        gotoxy(30,12);
        printf("2. Display All Record"); 
        gotoxy(30,14);
        printf("3. Edit a Record"); 
        gotoxy(30,16);
        printf("4. Delete a Record"); 
        gotoxy(30,18);
        printf("5. Back to Main Menu"); 
        gotoxy(30,20);
        printf("6. Exit"); 
        gotoxy(30,22);
        printf("Your Choice: "); 
        
		fflush(stdin);
        choice  = getche(); 
        
	    switch(choice)
        {
        case '1': 
            
			addemployee();
            break;
        
		case '2':
            displayemployee();
            getch();
            break;

        case '3': 
            editemployee();
            break;
        
		case '4':
            deleteemployee();
            break;
        
		case '5':
        	main();
        	break;
        	
		case '6':
            fclose(fp);
            exit(0);
        }
    }
    return;
}	



void addemployee()
{
			system("cls");
            fseek(fp,0,SEEK_END); 
            
            another = 'y';
            while(another == 'y')  
            {
                printf("\nEnter name: ");
                scanf("%s",e.name);
                
				printf("\nEnter age: ");
                scanf("%d", &e.age);
                
				printf("\nEnter salary: ");
                scanf("%f", &e.bs);

                fwrite(&e,recsize,1,fp); 

                printf("\nAdd another record(y/n) ");
                fflush(stdin);
                another = getche();
            }
        }
        
        
void displayemployee()
{
	        system("cls");
            rewind(fp); 
            printf("\n\n-------------------- List of Employees --------------------\n");
            printf("\n---------- NAME ---------- AGE ---------- SALARY ---------- \n");
			while(fread(&e,recsize,1,fp)==1)  
            {
                printf("\n             %s              %d              %.2f\n",e.name,e.age,e.bs); 
            }
}



void editemployee()
{
	system("cls");
            another = 'y';
            
			while(another == 'y')
            {
                printf("Enter the name of the employee that you want to edit: ");
                scanf("%s", empname);
                rewind(fp);
                
				while(fread(&e,recsize,1,fp)==1)  
                {
                    if(strcmp(e.name,empname) == 0)  
                    {
                        
                        printf("\nEnter new age: ");
                        scanf("%d",&e.age);
                        
                        printf("\nEnter new salary: ");
                        scanf("%f",&e.bs);
                        
						fseek(fp,-recsize,SEEK_CUR);
                        fwrite(&e,recsize,1,fp); 
                        break;
                    }
                }
                
				printf("\nEdit another record(y/n)");
                fflush(stdin);
                another = getche();
            }
}


void deleteemployee()
{
	        system("cls");
            another = 'y';
            
			while(another == 'y')
            {
                printf("\nEnter name of the employee to delete: ");
                scanf("%s",empname);
                ft = fopen("Temp.dat","wb"); 
                rewind(fp); 
                while(fread(&e,recsize,1,fp) == 1)  
                {
                    if(strcmp(e.name,empname) != 0) 
                    {
                        fwrite(&e,recsize,1,ft); 
                    }
                }
                fclose(fp);
                fclose(ft);
                remove("EMP.DAT"); 
                rename("Temp.dat","EMP.DAT"); 
                fp = fopen("EMP.DAT", "rb+");
                
				printf("Delete another record(y/n)");
                fflush(stdin);
                another = getche();
            }
}
