
import java.util.*;
class loan
{
    double[] bal=new double[100]; int[] AC=new int[100];  //maximum bank capacity =100 hence array size= 100
    Scanner sc = new Scanner(System.in);
    int c=0;
    void input()  //input function that takes all the required inputs from th euser and calls the respective functions accordingly 
    {  int i,accNo;
        for(i=0;i<100;i++)
         {
             System.out.println("\nEnter\n1-->New Account 2--->Old account 3--->END\n");
             int num=sc.nextInt();
             if(num==1) //for new acc. add it to the array
             {
             
             System.out.println("Enter Account no:\n ");
             AC[c]=sc.nextInt();
             accNo=AC[c];
             c++;
             }
             else if(num==2) //for old acc just take the input and check if acc is valid 
                {
                    System.out.println("Enter Account no:\n");
                    accNo=sc.nextInt();
                    if(check(accNo)==0)
                     {
                         System.out.println("Account does not exist. CREATE A NEW ACCOUNT ");
                         continue;
                     }
                     
                }
                else 
                {
                    System.out.println("BYE");
                  break;
                }
             System.out.println("Enter:\n1-->DEPOSIT\n2-->WITHDRAW\n3-->CHECK THE BALANCE\n4-->END");
            
             
             int n=sc.nextInt();
             switch(n) //switch case to perforn various operations acc to the user's input 
             {   
                 case 1: System.out.println("Enter amount to be deposited :");
                         deposit(accNo,sc.nextDouble()); break;
                case 2:  System.out.println("Enter amount to be withdrawn :");
                         withdraw(accNo,sc.nextDouble()); break;
                case 3 :System.out.println("BALANCE: " );
                        display(accNo);break;
                case 4: i=100;break;
                default :System.out.println("Invalid input, Enter again:");
                         i--;
                         continue;
                      
             }
              
         }
    }
    void deposit(int accNo, double amtD) //deposits the given amount 
    { int i;
        for(i=0;i<c;i++)
        {
            if(AC[i]==accNo)
            break;
        }
        bal[i]=bal[i]+amtD;
         System.out.println("Amount deposited ");
    }
    void withdraw(int accNo, double amtW) //withdrawing the given amount
    {int i;
        for(i=0;i<c;i++)
        {
            if(accNo==AC[i])
            break;
        }
        if(bal[i]-amtW < 500)
        System.out.println("Cannot withdraw...low balance");
        else
        {
            bal[i]=bal[i]-amtW;
             System.out.println("Amount withdrawn");
        }
    }
    void display(int accNo) //displaying the balance in the given account 
    { int i;
        for(i=0;i<c;i++)
        {
            if(AC[i]==accNo)
            System.out.println(bal[i]);
        }
    }
    
    int check(int accNo)
    {int flag=0;
        for(int i=0;i<c;i++)
        {
            if(accNo==AC[i])
             flag=1;
        }
        return flag;
        
    }
    public static void main(String[] args) 
    {
        new loan().input();
        
        
    }
}

//ANSWER TO THE QUESTION 
//the lending system here is centralized as the arrays of the accoungt and the balance are members of the class (global) the demerit of this is that it is prone to changes and regulation at the local level. 
