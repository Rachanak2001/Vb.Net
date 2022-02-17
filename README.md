**Binary Triangle**
using System;

namespace  Ex1
{
    class BinaryTriangle
    {
        static void Main(string[] args)
        {
            int number, digit = 1;
            Console.Write("\n Enter the number of lines: ");
            number = Convert.ToInt32(Console.ReadLine());
            for (int i = 1; i <= number; i++)
            {
                for (int space = number - i; space > 0; space--)
                {
                    Console.Write("");
                }
                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit + " ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}

**OUTPUT**





**AMICABLE NUMBER**
using System;

namespace ex4
{
    class AmicableNumber
    {
        static void Main(string[] args)
        {
            int num1, num2, sum1 = 0, sum2 = 0;
            Console.WriteLine("\n........AMICABLE NUMBERS........");
            Console.Write("\n Enter the first number: ");
            num1 = Convert.ToInt32(Console.ReadLine());
            Console.Write("\n Enter the second number: ");
            num2 = Convert.ToInt32(Console.ReadLine());
            for (int i = 1; i < num1; i++)
            {
                if (num1 % i == 0)
                {
                    sum1 += i;
                }
            }
            for (int i = 1; i < num2; i++)
            {
                if (num2 % i == 0)
                {
                    sum2 += i;
                }
            }
            if (sum1 == num2 && sum2 == num1)
            {
                Console.WriteLine("\n The number {0} and {1} are amicable.", num1, num2);
            }
            else
            {
                Console.WriteLine("\n The number {0} and {1} are not amicable.", num1, num2);
            }

        }
    }
}

**AMICABLE NUMBERS**
![image](https://user-images.githubusercontent.com/97940850/154425457-4d3bc1d3-a81d-4081-9b7d-4f8957e5ea39.png)





