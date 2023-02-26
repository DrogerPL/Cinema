package cinema;
import java.awt.*;
import java.util.Arrays;
import java.util.Scanner;
import java.lang.Math;

public class Cinema {

    public static char[][] CreateCinema(int a,int b)
    {
        char[][] twoDimArray = new char[a][b];
        for (int i = 0; i < a; i++)
        {
            for (int j = 0; j < b; j++)
            {
                twoDimArray[i][j] = 'S';
            }
        }
        return twoDimArray;
    }

    public static void PrintCinema(char[][]twoDimArray, int a,int b)
    {
        int x = 1;
        System.out.println("Cinema:");
        System.out.print(" ");
        for(int i=1;i<=b;i++)
        {
            System.out.print(" ");
            System.out.print(i);
        }
        System.out.println();
        for (int i=0;i<a;i++)
        {
            System.out.print(x++);
            for (int e=0;e<b;e++)
            {
                System.out.print(" ");
                System.out.print(twoDimArray[i][e]);
            }
            System.out.println();
        }
    }


    public static int ChooseSeat(int a, int b,int rows,int seats)
    {
        int numberOfPeople = rows * seats;
        int price ;
        if(numberOfPeople<=60)
        {
            price = 10;
        }
        else
        {
            double smallerHalf = rows/2 ;
            if(a<=smallerHalf)
            {
                price = 10;
            }
            else
            {
                price = 8;
            }
        }
        System.out.println("Ticket price: $"+price);
        return price;
    }

    public static void TotalIncome(int a, int b,int rows,int seats)
    {
        int numberOfPeople = rows * seats;
        int price ;
        if(numberOfPeople<=60)
        {
             price = numberOfPeople * 10;
        }
        else
        {
            double smallerHalf = rows/2 ;
             int biggerHalf = rows - (int)smallerHalf;
             price = (int)smallerHalf * seats * 10;
             price += biggerHalf * seats * 8;

              System.out.println(price);
        }
        System.out.println("Total income: $"+price);
    }

    public static double procentOfSeats(int numbeOfTickets, int totalSeats)
    {
       return (double)numbeOfTickets * 100 / (double)totalSeats;
    }

    public static boolean checkValue(int a,int b, int rows, int seats, char[][] twoDimArray)
    {
        if(a>rows || a<=0 || b>seats || b<=0)
        {
            System.out.println("Wrong input!");
            return false;
        }
        else if(twoDimArray[a-1][b-1] == 'B')
        {
            System.out.println("That ticket has already been purchased!");
          
            return false;
        }
        else
        {
            return true;
        }
    }

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = 0;
        int b = 0;
        int numberOfTickets = 0, income = 0;
        System.out.println("Enter the number of rows:");
        int rows = scan.nextInt();
        System.out.println("Enter the number of seats in each row:");
        int seats = scan.nextInt();
        int totalSeats = rows * seats;
        char[][] twoDimArray = CreateCinema(rows,seats);
        int wskaznik=-1;
        while (wskaznik!=0)
        {
            System.out.println("1. Show the seats");
            System.out.println("2. Buy a ticket");
            System.out.println("3. Statistics");
            System.out.println("0. Exit");
            wskaznik = scan.nextInt();
            switch (wskaznik)
            {
                case 1:
                    PrintCinema(twoDimArray,rows,seats);
                    break;
                case 2:
                    while(true)
                    {
                        System.out.println("Enter a row number:");
                        a = scan.nextInt();
                        System.out.println("Enter a seat number in that row:");
                        b = scan.nextInt();
                        if (checkValue(a, b, rows, seats, twoDimArray))
                        {
                            twoDimArray[a - 1][b - 1] = 'B';
                            income += ChooseSeat(a, b, rows, seats);
                            numberOfTickets++;
                            break;
                        }
                    }
                    break;
                case 3:
                     System.out.println("Number of purchased tickets: "+numberOfTickets);
                     System.out.printf("Percentage: %.2f", procentOfSeats(numberOfTickets,totalSeats));
                     System.out.print('%');
                     System.out.println();
                     System.out.println("Current income: $"+ income);
                     TotalIncome(a, b, rows, seats);
                     break;
                case 0:
                    wskaznik = 0;
                    break;
                default:
                    break;
            }
        }
    }
}
