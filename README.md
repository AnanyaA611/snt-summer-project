
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
             System.out.println("\nEnter:\n1-->New Account 2--->Old account"); 
             int num=sc.nextInt();
             if(num==1) //for new acc. acc it to the array
             {
             
             System.out.println("Enter Account no: ");
             AC[i]=sc.nextInt();
             accNo=AC[i];
             }
             else //for old acc just take the input 
                {
                    System.out.println("Enter Account no");
                    accNo=sc.nextInt();
                }
             System.out.println("Enter:\n1-->DEPOSIT\n2-->WITHDRAW\n3-->CHECK THE BALANCE\n4-->END");
            
             
             int n=sc.nextInt();  
             switch(n)  //switch case to perforn various operations acc to the user's input 
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
              c++;
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
    
    
    public static void main(String[] args) 
    {
        new loan().input();
        
        
    }
}


//ANSWER TO THE QUESTION 
//the lending system here is centralized as the arrays of the accoungt and the balance are members of the class (global) the demerit of this is that it is prone to changes and regulation at the local level. 
