
//**************************** Header files ********************************  * *
#include<iostream.h>
#include<conio.h>
#include<dos.h>
#include<string.h>
#include<stdio.h>
#include<fstream.h>

//*************************** End  of Header Files **************************
//*************************** class definition ******************************
class candidate
{ public :
  int UID,vote;
  char sex;
  char name[30];
  char class1[10];
       candidate(int x)
       {
	UID=x;
       }
   int castevote(int priority,int votedby);
   void details();
   void display();
      }noofcandi[10]={ 1,2,3,4,5,6,7,8,9,10}; //caste vote
//**************************** End of the claas function ********************
//****************************      class function definition  ***************
void candidate::details()    // detail function input
 {                                //detail function
   cout<<"--------------  Enter the name of candidate -------------------"
   <<endl<<endl;
   gets(name);
   cout<<endl<<endl;
   cout<<"---------------- Enter the class and section of the candidate -----------";
   cout<<endl<<endl;
   gets(class1);
   cout<<endl<<endl;
   cout<<" --------------- Enter the sex of the candidate --------------";
   cout<<endl<<endl;
   cin>>sex;


 }         // end of detail func

 void candidate:: display()             //detail function definition
 {
   cout<<"The name of the candidate is " ;puts(name);
   cout<<endl<<endl;
   cout<<"Class  " ;puts(class1);
   cout<<endl<<endl;
   cout<<"Unique ID OF the candidate is : -  "<<UID;
   cout<<endl<<endl;
}



int candidate :: castevote(int priority ,int votedby)
{
       switch(votedby)
	{

	 case 1:
		    if(priority==1)		//1 for principal
			   vote+=400;
		     if(priority==2)
			  vote+=200;
		    if(priority==3)
		      vote+=100;
			break;


	 case 2:                 // 2 for teacher
		  if(priority==1)
		    vote+=200;
		 if(priority==2)
		    vote+=100;
		 if(priority==3)
		    vote+=50;
		    break;

	 case 3:                // 3 for students

	       if(priority==1)
		   vote+=100;
	       if(priority==2)
		   vote+=50;
	       if(priority==3)
		   vote+=25;
		    break;
	 }  //switch statement

  return 0;
  } // function defintion
//**************** end of function definition ******************************
//***************** Result text file creation function***********************
 void result(int mcount,int fcount, int mindex[],int findex[])
 {
  ofstream fout;
  fout.open("result.txt",ios::out);
  fout<<" votess for the post of head boy "<<endl;
//******************** HEAD BOY CANDIDATE VOTES****************************
	for(int i=0,j=0;i<mcount;i++,j++)
	 { fout<<" U I D "<<" "<<noofcandi[mindex[j]-1].UID;
	   fout<<"name"<<noofcandi[mindex[j]-1].name<<" ";
	   fout<<"class"<<noofcandi[mindex[j]-1].class1<<" ";
	   fout<<"vots casted"<<noofcandi[mindex[j]-1].vote;
	   fout<<endl<<endl<< "end of details of candidate ";
	 }
//****************** END OF HEAD BOY CANDIDATES ***************************

//***************** HEAD GIRL CANDIDATES VOTES *****************************
  fout<<endl<<endl;
  fout<<" CANDIDATES FOR THE POST OF HEAD GIRL "<<endl<<endl;


	for( i=0,j=0;i<fcount;i++,j++)
	 { fout<<" U I D "<<" "<<noofcandi[findex[j]-1].UID;
	   fout<<"name"<<noofcandi[findex[j]-1].name<<" ";
	   fout<<"class"<<noofcandi[findex[j]-1].class1<<" ";
	   fout<<"vots casted"<<noofcandi[findex[j]-1].vote;
	   fout<<endl<<endl<< "end of details of candidate ";
	 }
//*************************** END OF HEAD GIRL CANDIDATES*******************

fout.close();
  cout<<" file successfully created";
 } // result function end

//*********************** END OF RESULT FUNCTION************************

//********************** Portals for casting vote *************************
void principal(int mcount,int fcount,int mindex[],int findex[])
{  int id,pass;
    clrscr();
    cout<<endl<<endl;
    cout<<" A U T H E N T I C A T I O N  R E Q U I R E D"<<endl<<endl;
    cout<<" U S E R  I D ";
    cin>>id;
    cout<<endl<<"P A S S W O R D ";
    cin>>pass;
    if(id!=3112||pass!=1234)
     {	cout<<"I N V A L I D  C R E D E N T I A L S";
	return;
     }


	cout<<endl<<" W E L C O M E  M R . P R I N C I P A L ";
	cout<<endl<<endl<<" C H O O S E  T H E  R E Q U I R E D  A C T I O N";
	cout<<endl<<"1. Caste vote";
	cout<<endl<<endl<<"2. Show result"<<endl;
	int princhoice;

	cin>>princhoice;

	if(princhoice==1)
	{  clrscr();
	 int  k=0;
	 cout<<"********************** Candidates for the post of head boy ************";
	      cout<<endl<<endl;

	for(int i=0;i<mcount;i++,k++)
	{
	cout<<" DO REMEMBER THE UID TO CASTE THE VOTE TO THE CANDIDATE"<<endl;
	cout<<" Displaying details  of candidate"<<endl<<endl;
	noofcandi[mindex[k]-1].display();
	cout<<"*********************End of the details of "<<i+1<<"candidate************";
	 cout<<endl<<"Press enter to proceed "<<endl;
	getch();
	clrscr();

   }// end of for loop
//***************************************************************************
	 int prior[3];// to check so that no candidate is given dual priority

	 int candivote[3]={-1,-1,-1}; // check for the repeating voting for a single candidate

	 int m=0;

 //******************* casting vote to head boy *****************************
	 clrscr();
    while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<mcount;o++)
	 { if(voteuid==mindex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }

	 if(flag==0)
	   {
	   cout<<" Invalid Selection"<<endl;
	   continue;
	   }
	if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate "<<endl;
			  cout<<"again select the candidate "<<endl;
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
		 if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{
			cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}

			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned"<<endl;
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,1);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop





//********************** Printing the candidates for the post of head girl

   cout<<endl<<"Press Enter to see the list of the candidates for"<<endl
   <<"the post of head girl"<<endl;

		getch();
		clrscr();k=0  ;

	 cout<<"  ********* Candidates for the post of head girl************";
	 cout<<endl<<endl;

  for(i=0;i<fcount;i++,k++)
    {
    cout<<" Do REMEMBER THE UID TO CASTE VOTE ";
     cout<<endl<<endl<<" Displaying details  of candidate"<<endl<<endl;
     noofcandi[findex[k]-1].display();
     cout<<endl<<endl;
     cout<<"*********************End of the details of "<<i+1<<"candidate************";
      cout<<endl<<"Press enter to proceed ";
    getch();
    clrscr();

   }// end of for loop
//**************************** casting vote to head girl*******************
	    candivote[0]=-1;
	    candivote[1]=-1;
	    candivote[2]=-1;
	     m=0;
	     prior[0]=0;
	     prior[1]=0;
	     prior[2]=0;

	while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<fcount;o++)
	 { if(voteuid==findex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }
	 if(flag==0)
	 { cout<<"invalid selection "<<endl;
	   continue;
	  }

	      if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate ";
			  cout<<"again select the candidate ";
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
		     if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}
			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned";
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,1);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop






	getch();

	}// end of if

 //**** ***************** END Of  MENU 1 *************************************

//************************ MENU  2 *****************************************

    if(princhoice==2)
    {
     cout<<" A U T H E N T I C A T E  Y O U R S E L F ";
     cout<<endl<<"USER ID :"<<endl;
     cin>>id;
     cout<<"PASSWORD : "<<endl;
     cin>>pass;
    if(id!=3112||pass!=1234)
     {	cout<<"I N V A L I D  C R E D E N T I A L S";
	return;
     }

     result(mcount,fcount,mindex,findex);// calling for creating result function
    }// menu 2 end

    if(princhoice!=2||princhoice!=1)
      { clrscr();
	cout<<endl<<endl<<endl<<" I N V A L I D  C H O I C E";
	return ;

      }







 }//principal portal ending--------------------------------------------------







 //************************** Faculty portal*********************************
 void faculty(int mcount,int fcount,int mindex[],int findex[],int facultyvoter[],int * votercountf)
   {   int userid; int password;
       int facultyid;int facultypass;
   cout<<endl<<endl<<"      WELCOME TO THE FACULTY PORTAL   "<<endl<<endl;
   cout<<"      2 - Step verification id required "<<endl<<endl;
   cout<<" ENTER THE FACULTY ID AND PASSWORD"<<endl;

   cout<<" Faculty Username : ";
   cin>>facultyid;
   cout<<endl;
   cout<<" Faculty Password : ";
   cin>>facultypass;
	if(facultyid!=1234||facultypass!=3112)
	   {  cout<<"Wrong id or password "<<endl;
	      cout<<" Authentication failed"<<endl;
	      delay(1000);
	      return;
	   }


   cout<<endl<<endl<<"                A U T H E N T I C A T E   Y O U R S E L F ";
   cout<<endl<<endl<<" U S E R I D "<<endl;
   cin>>userid;
   cout<<endl;
   cout<<" P A S S W O R D "<<endl;
   cin>>password;
   cout<<endl;

   for(int i=0;i<=*votercountf;i++)
		   { if(userid==facultyvoter[i])
		       { cout<<"votr already casted ";
			 return;


		      }
		    cout<<" value of facultyvoter[i]"<<"  " <<facultyvoter[i];

		   }


   ifstream fin;
   fin.seekg(0) ;
   fin.open("faculty.txt",ios::in);
      int wrong=0;
	while(!fin.eof())
	   { cout<<endl<<endl<<" using data file handling"<<endl;

	   int id;
	     int code;
	      fin>>id;
	      fin>>code;
	      if(id==userid&&code==password)
	      {
	       facultyvoter[*votercountf]=userid;
	      *votercountf++;
	       wrong=0;
		  break;
	      } //end of if

	 wrong=-1;


     }//end of while

       fin.close();
	  if(wrong==-1)
	{   cout<<"wrong user id or pasword";
		return;
	 }



//common code for casting vote to the candidates ------------------------

	  clrscr();
	 int  k=0;
	 cout<<"********************** Candidates for the post of head boy ************";
	      cout<<endl<<endl;

    for( i=0;i<mcount;i++,k++)
	{
	cout<<" DO REMEMBER THE UID TO CASTE THE VOTE TO THE CANDIDATE"<<endl;
	cout<<" Displaying details  of candidate"<<endl<<endl;
	noofcandi[mindex[k]-1].display();
	cout<<"*********************End of the details of "<<i+1<<"candidate************";
	 cout<<endl<<"Press enter to proceed "<<endl;
	getch();
	clrscr();

       }// end of for loop
//***************************************************************************
	 int prior[3];// to check so that no candidate is given dual priority

	 int candivote[3]={-1,-1,-1}; // check for the repeating voting for a single candidate

	 int m=0;

 //******************* casting vote to head boy *****************************
	 clrscr();
    while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<mcount;o++)
	 { if(voteuid==mindex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }

	 if(flag==0)
	   {
	   cout<<" Invalid Selection"<<endl;
	   continue;
	   }
	if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate "<<endl;
			  cout<<"again select the candidate "<<endl;
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
			 if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}

			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned"<<endl;
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,2);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop





//********************** Printing the candidates for the post of head girl

   cout<<endl<<"Press Enter to see the list of the candidates for"<<endl
   <<"the post of head girl"<<endl;

		getch();
		clrscr();k=0  ;

	 cout<<"  ********* Candidates for the post of head girl************";
	 cout<<endl<<endl;

  for(i=0;i<fcount;i++,k++)
    {
    cout<<" Do REMEMBER THE UID TO CASTE VOTE ";
     cout<<endl<<endl<<" Displaying details  of candidate"<<endl<<endl;
     noofcandi[findex[k]-1].display();
     cout<<endl<<endl;
     cout<<"*********************End of the details of "<<i+1<<"candidate************";
      cout<<endl<<"Press enter to proceed ";
    getch();
    clrscr();

   }// end of for loop
//**************************** casting vote to head girl*******************
	    candivote[0]=-1;
	    candivote[1]=-1;
	    candivote[2]=-1;
	     m=0;
	     prior[0]=0;
	     prior[1]=0;
	     prior[2]=0;

	while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<fcount;o++)
	 { if(voteuid==findex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }
	 if(flag==0)
	 { cout<<"invalid selection "<<endl;
	   continue;
	  }

	      if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate ";
			  cout<<"again select the candidate ";
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
		   if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}

			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned";
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,2);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop






	getch();





} // end of the faculty portal ----------------------------------------------






//********************************** Student portal *************************

 void student(int mcount,int fcount,int mindex[],int findex[],int studentvoter[],int * votercountstu)
   {   int userid; int password;

   cout<<endl<<endl<<"      WELCOME TO STUDENT PORTAL   "<<endl<<endl;

   cout<<endl<<endl<<"                A U T H E N T I C A T E   Y O U R S E L F ";
   cout<<endl<<endl<<" U S E R I D "<<endl;
   cin>>userid;
   cout<<endl;
   cout<<" P A S S W O R D "<<endl;
   cin>>password;
   cout<<endl;

   for(int i=0;i<=*votercountstu;i++)
		   { if(userid==studentvoter[i])
		       { cout<<"votr already casted ";
			 return;


		      }


		   }


   ifstream fin;
   fin.seekg(0) ;
   fin.open("student.txt",ios::in);
      int wrong=0;
	while(!fin.eof())
	   { cout<<endl<<endl<<" using data file handling"<<endl;

	   int id;
	     int code;
	      fin>>id;
	      fin>>code;
	      if(id==userid&&code==password)
	      {
	       studentvoter[*votercountstu]=userid;
	      *votercountstu++;
	       wrong=0;
		  break;
	      } //end of if

	 wrong=-1;


     }//end of while

       fin.close();
	  if(wrong==-1)
	{   cout<<"wrong user id or pasword";
		return;
	 }



//common code for casting vote to the candidates ------------------------

	  clrscr();
	 int  k=0;
	 cout<<"********************** Candidates for the post of head boy ************";
	      cout<<endl<<endl;

    for( i=0;i<mcount;i++,k++)
	{
	cout<<" DO REMEMBER THE UID TO CASTE THE VOTE TO THE CANDIDATE"<<endl;
	cout<<" Displaying details  of candidate"<<endl<<endl;
	noofcandi[mindex[k]-1].display();
	cout<<"*********************End of the details of "<<i+1<<"candidate************";
	 cout<<endl<<"Press enter to proceed "<<endl;
	getch();
	clrscr();

       }// end of for loop
//***************************************************************************
	 int prior[3];// to check so that no candidate is given dual priority

	 int candivote[3]={-1,-1,-1}; // check for the repeating voting for a single candidate

	 int m=0;

 //******************* casting vote to head boy *****************************
	 clrscr();
    while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<mcount;o++)
	 { if(voteuid==mindex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }

	 if(flag==0)
	   {
	   cout<<" Invalid Selection"<<endl;
	   continue;
	   }
	if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate "<<endl;
			  cout<<"again select the candidate "<<endl;
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
			 if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}

			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned"<<endl;
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,3);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop





//********************** Printing the candidates for the post of head girl

   cout<<endl<<"Press Enter to see the list of the candidates for"<<endl
   <<"the post of head girl"<<endl;

		getch();
		clrscr();k=0  ;

	 cout<<"  ********* Candidates for the post of head girl************";
	 cout<<endl<<endl;

  for(i=0;i<fcount;i++,k++)
    {
    cout<<" Do REMEMBER THE UID TO CASTE VOTE ";
     cout<<endl<<endl<<" Displaying details  of candidate"<<endl<<endl;
     noofcandi[findex[k]-1].display();
     cout<<endl<<endl;
     cout<<"*********************End of the details of "<<i+1<<"candidate************";
      cout<<endl<<"Press enter to proceed ";
    getch();
    clrscr();

   }// end of for loop
//**************************** casting vote to head girl*******************
	    candivote[0]=-1;
	    candivote[1]=-1;
	    candivote[2]=-1;
	     m=0;
	     prior[0]=0;
	     prior[1]=0;
	     prior[2]=0;

	while(1){
	      if(prior[0]==-1&&prior[1]==-1&&prior[2]==-1)
		 {clrscr();
		  cout<<" Vote casted successfully "<<endl;
		  cout<<" Thank you "<<endl;
		  break;
		  }


	 int voteuid,votepriority,flag=0;
	 cout<<"Select the UID to caste vote for the candidate"<<endl;
	 cin>>voteuid;
	for(int o=0;o<fcount;o++)
	 { if(voteuid==findex[o])
	    { cout<<" VALID SELECTION OF CANDIDATE "<<endl;
	      flag=1;
	     break;
	    }

	 }
	 if(flag==0)
	 { cout<<"invalid selection "<<endl;
	   continue;
	  }

	      if(candivote[0]==voteuid||candivote[1]==voteuid||candivote[2]==voteuid)
			{ cout<<"vote already casted top this candidate ";
			  cout<<"again select the candidate ";
			  continue;

			 }
		cout<<"enter the priority 1,2 or 3 "<<endl;
		cin>>votepriority;
		   if(votepriority!=1&&votepriority!=2&&votepriority!=3&&votepriority!=-1)
			{cout<<endl<<" invalid selection of priotity";
			cout<<endl<<endl;
			continue;
			}

			if(prior[votepriority-1]== -1)
			 { cout<<" priority already assigned";
			   cout<<endl<<"redirecting to again choosing";
			   continue;
			 }

		noofcandi[voteuid-1].castevote(votepriority,3);
		candivote[m]=voteuid;
		m++;
		prior[votepriority-1]=-1;



	       } // while loop






	getch();





} // end of the student  portal --------------------------------------------








int main()
{  int facultyvoter[400];
   int votercountf=0;	                        //main fucntion
   int studentvoter[1000];
   int votercountstu=0;
	 clrscr();
//**********************  main page ****************************************
//*********************** Variable declaration******************************
int userid,password;    //principal userid and password


//******** adding design to the page ***************************************

 for(int i=0;i<5;i++)
    { for(int j=0;j<15;j++)
       {
       cout<<"- * -";
       }delay(200);
       cout<<endl;

   }
 //********* end to the design  of the page  *******************************
 cout<<endl<<endl<<endl;
 cout<<"      P R E F E C T O R I A L ";
 cout<<"      E L E C T I O N         "<<endl<<endl;
 cout<<"++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++"
 <<endl<<endl;
  delay(100);
 cout<<"  V O T E   T O D A Y "
<<endl<<"                       I T   W I L L  R E F L E C T  "  <<endl
<<endl<<"                                                  Y O U R   T O M O R R O W ";

 cout<<endl<<endl<<endl<<endl<<endl;
   delay(150);

//******** adding design to the page ***************************************

 for( i=0;i<5;i++)
    { for(int j=0;j<15;j++)
       {
       cout<<"- * -";
       }
       delay(200);
       cout<<endl;

   }
 //********* end to the design  of the page  *******************************

   clrscr(); //moving to second page

//*********************** Setting up the election **************************

 for( i=0;i<5;i++)
    { for(int j=0;j<15;j++)
       {
       cout<<"- $ -";
       }delay(200);
       cout<<endl;

   }

cout<<"W E L C M E   M R. P R I N C I P L "<<endl<<endl<<endl;
for(i=3;i>0;i--)
  {
	cout<<"************ A U T H E T I C A T E  Y O U R S E L F  ********"<<endl<<endl;
	cout<<"        U S E R I D : "<<endl;
	cin>>userid; // pricipal username and password required
	cout<<"        P A S S W O R D : "<<endl;
	cin>>password;
	cout<<endl<<endl;
	if(userid!=3112||password!=1234)
	  {
		cout<<" XXXXXXXX A U T H E N T I C A T I O N  F A I L E D XXXXXXXXXXXXX"<<endl<<endl<<endl;
		cout<<" I N V A L I D  U S E R N A M E  O R  P A S S W O R D" ;
		cout<<endl<<endl;
		cout<<"A T T E M P T S  L E F T : " <<i;

		delay(3000);
		clrscr();
	  if(i==1)
	    { cout<<"********************** A L E R T *********************************";
	       delay(4000);
	       return 0;
	     } // if statement terminating the whole program




	  }  //if statement of authentication of setup;
    else
      {
      break;
       }

  }// for loop termination
//********************************* Candidates entering their names *******

clrscr();
cout<<">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>";
cout<<endl;
cout<<">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>";
cout<<endl;
cout<<">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>";
cout<<endl;
cout<<" M R . P R I N C I P A L " <<endl;
cout<<" E N T E R   T H E  C R E D E N T I A L S";
cout<<endl;
cout<<" *******************************************************************";
cout<<endl;
cout<<"N O T E :  You Won't be able to due changes after wards"<<endl;
cout<<endl<<"Be  careful while filling the inormation"<<endl;
cout<<"  Directing you towards the portal of filling details of candidates";
cout<<endl<<endl;
delay(4000);
clrscr();

 for( i=0;i<5;i++)
    { for(int j=0;j<15;j++)
       {
       cout<<"- * -";
       }delay(200);
       cout<<endl;

   }       char choice='y';
	   int totalcandi=0; // total number of candidate
     i=0;
	do
	  {
	  noofcandi[i].details();
	  delay(50);
	  cout<<"---------------- Completition of details of candidate number";
	   cout<<endl<<endl;
	  totalcandi++;

	  clrscr();
	   cout<<" Want to enter more candidates or not   (Y/N)";
	     cout<<endl<<endl;
	   cin>>choice;
	     cout<<endl;
	     i++;
	  } while(choice=='y');
cout<<endl<<endl<<endl;
cout<<"  The Database of candidates are created successfully";
cout<<endl<<endl;
cout<<"Displaying the entire database to you "<<endl<<endl;

     for(i=0;i<40;i++)
      {
      cout<<".";
      delay(100);
      }
//*************************************************************************
//**************** Displaying the database ********************************
   int mcount=0,fcount=0;
       int mindex[10],findex[10];
	 int k=0,l=0;
  for(i=0;i<totalcandi;i++)
   {
    if(noofcandi[i].sex=='m')

     { mcount++;
       mindex[k]=noofcandi[i].UID;
       k++;
     }
     else
       {	fcount++;
		findex[l]=noofcandi[i].UID;
		l++;
       }

   }  //end of the for

//*********************** Printing only candidates for the post of head boy
 clrscr();
 k=0;
 cout<<"********************** Candidates for the post of head boy ************";
 cout<<endl<<endl;

  for(i=0;i<mcount;i++,k++)
    {

     cout<<" Displaying details  of candidate"<<endl<<endl;
      noofcandi[mindex[k]-1].display();
     cout<<"*********************End of the details of "<<i+1<<"candidate************";
     cout<<endl<<"Press enter to proceed "<<endl;
     getch();
     clrscr();

   }// end of for loop
//***************************************************************************

//********************** Printing the candidates for the post of head girl

   cout<<endl<<"Press Enter to see the list of the candidates for"<<endl
   <<"the post of head girl"<<endl;

getch();
   clrscr();k=0  ;

 cout<<"  ********* Candidates for the post of head girl************";
 cout<<endl<<endl;

  for(i=0;i<fcount;i++,k++)
    {

     cout<<endl<<endl<<" Displaying details  of candidate"<<endl<<endl;
     noofcandi[findex[k]-1].display();
     cout<<endl<<endl;
     cout<<"*********************End of the details of "<<i+1<<"candidate************";
      cout<<endl<<"Press enter to proceed ";
    getch();
    clrscr();

   }// end of for loop
//***************************************************************************
cout<<endl<<endl;
cout<< " E L E C T I O N"<<endl;
cout<<"           S E T  U P "<<endl;
cout<< "                S U C C E S S F U L L Y"<<endl;
delay(900);
//*************** End of phase 1 election set up ***************************

//**************** Phase 2 :- casting vote initiated **********************
      int comeout=0;
	do

	{
	int portalcaste;
	 cout<<endl<<endl<<" W H O  A R E  Y O U "<<endl<<endl;
	  cout<<"1:  P R I N C I P A L"<<endl;
	  cout<<"2:  F A C U L T Y "<<endl;
	  cout<<"3:  S T U D E N T "<<endl;
	  cin>>portalcaste;

	//*--------- principal portal invoked -----------------*
	  switch(portalcaste)
	      {
	      case 1: principal(mcount,fcount,mindex,findex);
			   break;
	      case 2: faculty(mcount,fcount,mindex,findex,facultyvoter,&votercountf);
		       break;
	      case 3: student(mcount,fcount,mindex,findex,studentvoter,&votercountstu );
		      break;


	      case 4:   comeout=-1;
			break;
	      default: continue;
	      }

	 if(comeout==-1)
	    break;
	  }while(1);// end of do while



//***************************************************************************
   getch();
   return 0;

   }   //main()

