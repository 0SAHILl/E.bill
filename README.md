SAHIL SINGHAL
# E.bill
#include <stdio.h>

void display() {
    printf("\n    Units          Rate/unit\n");
    printf("------------------------------\n");
    printf("    0-50             Rs 2\n");
    printf("    51-150           Rs 3\n");
    printf("    151-250          Rs 5\n");
    printf("    251-500          Rs 6\n");
    printf("    501 and above    Rs 8\n");
}

int calculateBill(int unit) { 
     int amount;
      if(unit<=50) {
        amount=unit*2;
    }
    else if(unit<=150)
    {
        amount=(50*2)+((unit-50)*3);
    }
    else if((unit<=250)){
        amount=(50*2)+((150-50)*3)+((unit-150)*5);
    }
    else if((unit<=500)){
        amount=(50*2)+((150-50)*3)+((250-150)*5)+((unit-250)*6);
    }
    else{
        amount=(50*2)+((150-50)*3)+((250-150)*5)+((500-250)*6)+((unit-500)*8);
    }
    return amount;
}


int main() {
char name[50];
int choice, units,total;
printf("WELCOME TO ONLINE ELECTRICITY BILL GENERATOR\n");
printf("\nPlease enter your name : ");
scanf("%s", &name);
//printf("loading...\n\n");
printf("\nHi %s, Please enter corresponding number to display your choice - \n",name);
printf("\n1 : to display prices per unit.\n2 : to calculate and display your bill.\nRandom key : to exit.\n");
printf("\nYour choice : ");
scanf("%d", &choice);
 
 switch(choice)
 {
     case 1:
     display();
     break;
     
     case 2:
     printf("\nPlease enter your units consumed : ");
     scanf("%d", &units);
     total = calculateBill(units);
     printf("\n%s, your electricity bill total is Rs %d.\n", name, total);
     break;

     default:
     break;
 }
  printf("\nThankyou for using the online electricity bill generator, have a good day.");    
  return 0;
}
