#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <math.h>

#define eps 0.0001

unsigned int method_select( void );
double f( double x );
void print_result(double a, double b, unsigned int n, double I );
double left_rectangle( double a, double b, unsigned int n );
double right_rectangle( double a, double b, unsigned int n );
double trap( double a, double b, unsigned int n );
double simpson( double a, double b, unsigned int n );

int main()
{
    unsigned int num_of_method;
    const double a = 1;
    const double b = 3;
    unsigned int n = 100;
    double I;
    double I1, I2;
    unsigned int N;
    num_of_method  =  method_select();

    if (num_of_method == 1 ){
        I = left_rectangle(a, b, n);
        print_result(a, b, n, I);
        N = 0;
              do{
           N = N + 2;
           I1 = left_rectangle(a, b, N);
           I2 = left_rectangle(a, b, N+2);
        }while(  fabs(I2-I1) > eps );
        printf("\n\nN=%u,  I1(N)=%.8lf\n", N, I1);




    }
    else if( num_of_method == 2 ){
        I=right_rectangle(a, b, n);
        print_result(a, b, n, I);

        N = 0;
       do{
           N = N + 2;
           I1 = right_rectangle(a, b, N);
           I2 = right_rectangle(a, b, N+2);
        }while(  fabs(I2-I1) > eps );

        printf("\n\nN=%u,  I1(N)=%.8lf\n", N, I1);

    }else if( num_of_method == 3 ){
        I=trap(a, b, n);
        print_result(a, b, n, I);

       N = 0;
       do{
           N = N + 2;
           I1 = trap(a, b, N);
           I2 = trap(a, b, N+2);
        }while(  fabs(I2-I1) > eps );

        printf("\n\nN=%u,  I1(N)=%.8lf\n", N, I1);
    }
    else if ( num_of_method == 4 ){

         I=simpson(a, b, n);
         print_result(a, b, n, I);

         N = 0;
       do{
           N = N + 2;
           I1 = simpson(a, b, N);
           I2 = simpson(a, b, N+2);
        }while(  fabs(I2-I1) > eps );

        printf("\n\nN=%u,  I1(N)=%.8lf\n", N, I1);

    }



    return 0;
}
unsigned int method_select(void)
{
    unsigned int temp;

    printf("\n\n Choose your method:\n1 - left \n2 - right \n3 - trap \n4 - Simpson\n>");
    scanf("%u", &temp);

    while(  temp < 1  ||   temp > 4 ){
        printf("\n!!!!Invalid data. Method: 1, 2, 3 or 4: ");
        scanf("%u", &temp);
    }

    switch(temp){
      case 1:
             printf("\nYou chose method of LEFT RECTANGLE");
             break;

      case 2:
             printf("\nYou chose method of RIGHT RECTANGLE");
             break;

      case 3:
             printf("\nYou chose method of TRAPEZOID");
             break;

      case 4:
             printf("\nYou chose method of SIMPSON");
             break;
    }


    return temp;
}
double f( double x )
{
    double y;

    y = x/(2*x*x+3*x-2);

    return y;
}
double left_rectangle(double a, double b, unsigned int n)
{
    double h;
    unsigned int k;
    double x;
    double sum = 0;

    h = ( b - a ) / n;
    x = a;

    for (k = 0;  k <= n-1;  k++ ){
      sum = sum + f(x);
      x = x + h;
    }

   return sum * h;
}

double right_rectangle(double a, double b, unsigned int n)
{
    double h;
    unsigned int k;
    double x;
    double sum = 0;

    h = ( b - a ) / n;
    x = a+h;

    for (k = 0;  k <= n-1;  k++ ){
      sum = sum + f(x);
      x = x + h;
    }

   return sum * h;
}

double trap(double a, double b, unsigned int n)
{
    double h;
    unsigned int k;
    double x;
    double sum = 0;
    double tes;

    h = ( b - a ) / n;
    x = a+h;

    for (k = 0;  k <= n-1;  k++ ){
      sum = sum + f(x);
      x = x + h;
    }
    tes = (f(a)/2)+sum+(f(b)/2);

   return tes * h;
}

   double simpson(double a, double b, unsigned int n)
{
    double h;
    unsigned int k;
    double x;
    double sum = 0;
    double sum1 = 0;
    double pot;

    h = ( b - a ) / n;
    x = a+h;

    for (k = 0;  k <= n-1;  k++ ){
      sum = sum +f(x);
      x= x + h;
    }
    x = a+(2*h);
    for (k = 2;  k <= n-1;  k+=2){
        sum1 = sum1 + f(x);
        x=x+h;
    }
        pot = f(a)+(4*sum)+(2*sum1)+f(b);

   return pot*h/3;
}
void print_result(double a, double b, unsigned int n, double I)
{
    system("cls");
    printf("\n***********************");
    printf("\n*       Results       *");
    printf("\n***********************\n");

    printf("a=%.2lf  b=%.2lf   n=%u    I = %.8lf", a, b, n, I);


}
