**1 C# program to find a Binary Triangle**<br>
using System;<br>

namespace  Ex1<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.Write("\n Enter the number of lines: ");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i <= number; i++)<br>
            {<br>
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write("");<br>
                }<br>
                for (int j = 0; j < i; j++)<br>
                {<br>
                    Console.Write(digit + " ");<br>
                    digit = (digit == 1) ? 0 : 1;<br>
                }<br>
                Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154625384-e7e3aaf3-a8ea-4f9d-b5c4-e532eb1be5a6.png)





**2 C# program to check whether the entered number is an AMICABLE NUMBER or not**<br>
using System;<br>

namespace ex4<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n........AMICABLE NUMBERS........");<br>
            Console.Write("\n Enter the first number: ");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\n Enter the second number: ");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {<br>
                Console.WriteLine("\n The number {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\n The number {0} and {1} are not amicable.", num1, num2);<br>
            }<br>

   }<br>
   }<br>
}<br>

**AMICABLE NUMBERS**<br>
![image](https://user-images.githubusercontent.com/97940850/154425457-4d3bc1d3-a81d-4081-9b7d-4f8957e5ea39.png)


**3 C# Program to Illustrate multilevel iinheritance with virtual methods(displaying student details**<br>
using System;<br>
namespace ex7<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n.......PERSONAL DETAILS.....\n");<br>
            Console.WriteLine("Name   :" + name);<br>
            Console.WriteLine("Age   :" + age);<br>
            Console.WriteLine("gender   :" + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regno;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regno, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regno = regno;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()
        {<br>
            base.Display();<br>
            Console.WriteLine("\n......COURSE DETAILS.......\n");<br>
            Console.WriteLine("Register Number: " + regno);<br>
            Console.WriteLine("Course: " + course);<br>
            Console.WriteLine("Semester: " + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] Marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regno, string course, int semester, int[] marks) : base(name, age, gender, regno, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.Marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "first class";<br>
            else if (average >= 50)<br>
                grade = "second class";<br>
            else<br>
                grade = "pass class";<br>

   }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n.......MARKS DETAILS.....\n");<br>
            Console.WriteLine("Marks in 5 subjects: ");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(Marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total: " + total);<br>
            Console.WriteLine("average: " + average);<br>
            Console.WriteLine("Grade: " + grade);<br>
        }<br>
    }<br>
    class MultiLevel<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails student1 = new MarksDetails("Rachana", 21, "Female", 20220001, "MSC", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            student1.Display();<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154626694-c7dd0f27-98a1-49b7-a5b0-21f4c798d34a.png)


**4 C# Program to create Gray code.**<br>
using System;<br>
namespace ex5<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\n Enter the decimal number: ");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Binary equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\n Gray code equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154627708-35d4a651-5ff5-41bb-b926-12551da4043b.png)


  **5 C# Program to calculate volume of 2 boxes and find the resultant volume after addition of 2 boxes by implementing operator overloading.** <br>
  using System;<br>
namespace ex6<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float lenght;<br>
        public float volume<br>
        {<br>
            get { return width * height * lenght; }<br>
        }<br>
        public Box(float width, float height, float lenght)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.lenght = height;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.volume + box2.volume;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return "box with width" + width + ",height" + height + "and lenght" + lenght;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    { <br>
        public static void Main()<br>
        {<br>
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is:{1}",box1,box1.volume);<br>
            Console.WriteLine("Volume of {0} is:{1}", box2, box2.volume);<br>
            Console.WriteLine("Volume after adding boxes:{0}", box1+box2);<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154629037-e5ce95da-8ea2-43b8-8adb-a954ce89e3c8.png)


**6 C# Program to implement principles of Delegate converting input string to uppercase first,last and entire string**<br>
using System;<br>
namespace ex8<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0]=char.ToUpper(buffer[0]);<br>
            return new string (buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length-1] = char.ToUpper(buffer[buffer.Length-1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input,UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("Input String:{0}",input);<br>
            Console.WriteLine("Output String:{0}", del(input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseAll));<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154629823-19042002-29d9-48e0-b7b6-25d620c9ef5a.png)


**7 C# program to generate Rigister number automatically for 100 student using static Constructor**<br>
using System;<br>
namespace ex9<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNO;<br>
        static int startNum;<br>
        static RegisterNum()<br>
        {<br>
            startNum=20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNO = ++startNum;<br>
        }<br>
        public static void Main(string[] args)<br>
        {<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("Student {0}:{1}",i+1,Student.regNO);<br>
            }<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154630837-497cda04-9cc8-475c-806f-66163dcc091b.png)
![image](https://user-images.githubusercontent.com/97940850/154631120-f7e8f60d-bd41-4964-a573-558c35734e4a.png)


**8 C# Program to find the frequency of the word "is" in a given sentence**<br>
using System;<br>
namespace ex10<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputString;<br>
            Console.WriteLine("\n........FREQUENCY OR WORD 'is'.........");<br>
            Console.WriteLine("\n Enter the input string: ");<br>
            inputString = Console.ReadLine();<br>
            char[] seperator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputString.ToLower();<br>
            string[] outcomes = testString.Split(seperator);<br>
            foreach(String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in '" + inputString + "'is: " + count);<br>

   }<br>
  }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154631764-8376067d-b911-4d81-9600-94c94ab3baee.png)


**9 C# program to benchmark 2D,Jagged array allocation**<br>
using System;<br>
using System.Diagnostics;<br>
namespace ex11<br>
{<br>
    class BenchmarkAllocation<br>
    {<br>
        const int _max= 100000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>
            for(int i = 0;i < 100;i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for(int i=0;i<_max;i++)<br>
            {<br>
                for (int j = 0; j<100; j++)<br>
                {<br>
                    for (int k = 0;  k<100;k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for(int i=0;i<_max;i++)<br>
          {<br>

   for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                    }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>
            Console.WriteLine("\n time taken for allocation in case of 2D array: ");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds+"miliseconds");<br>
            Console.WriteLine("\n Time taken for allocation in case of jagged array: ");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "miliseconds");<br>
        }<br>

   }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154632673-45f0f879-5bfd-47fe-9723-0f9075cb4543.png)



**10 C# program to find the sum of the values in diagonal of the matrix**<br>

 using System;<br>

namespace ex10 { class SumOfDiagonals<br>
{ static void Main(string[] args)<br>
{<br>
int MaxRow, MaxCol, Sum = 0;<br>
int[,] Matrix;<br>

Console.WriteLine("\n---------- SUM OF DIAGONAL OF A MATRIX ----------\n"); Console.Write("\nEnter the number of rows: ");<br>
MaxRow = Convert.ToInt32(Console.ReadLine());<br>
Console.Write("\nEnter the number of columns: ");<br>
MaxCol = Convert.ToInt32(Console.ReadLine());<br>
if (MaxRow != MaxCol)<br>
{<br>
Console.WriteLine("\nThe Dimensions entered are not of Square Matrix."); Console.WriteLine("\nExiting the Program..");<br>
return;<br>
<br>
} Matrix = new int[MaxRow, MaxCol];<br>

for (int i = 0; i < MaxRow; i++)<br>
{ for (int j = 0; j < MaxCol; j++)<br>
{ Console.Write("\nEnter the ({0},{1})th element of the matrix: ", (i + 1), (j + 1)); Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
}<br>
}<br>
Console.WriteLine("\nThe entered Matrix is: ");<br>
for (int i = 0; i < MaxRow; i++)<br>
{ for (int j = 0; j < MaxCol; j++)<br>
{<br>
Console.Write(" " + Matrix[i, j]);<br>
if (i == j)<br>
{<br>
Sum += Matrix[i, j];<br>
}<br>
}<br>
Console.WriteLine();<br>
} Console.WriteLine("\nThe Sum of Diagonal is " + Sum); }<br>
}<br>
}<br>

![image](https://user-images.githubusercontent.com/97940850/154633617-d4c0cfbd-1716-4701-a7c4-dcb4baffae82.png)<br>



**11. C# Program to Create a file check the existence of a file and read the content of the file**<br>
using System;<br>
using System.IO;<br>
namespace ex14<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n.......MENU.....\n");<br>
                Console.WriteLine("\n1. Create a File");<br>
                Console.WriteLine("\n2. Existence of  a File");<br>
                Console.WriteLine("\n3. Read the content of a File");<br>
                Console.WriteLine("\n4. Exit");<br>
                Console.Write("\n enter your choice: ");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\n Enter the file name to create: ");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\n write the content to the file: \n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is created...");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\n Enter the file name: ");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exists...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exist in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("\n Enter the file name to read the content: ");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = " ";<br>
                                Console.WriteLine("here is the content of the file: ");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine(" ");<br>
                            }<br>
                        }<br>
                        else<br>
                        {
                            Console.WriteLine("File does not exixts");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
                }<br>
            }<br>


   }<br>
   }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154637104-3b7c6fdd-7cf8-4c8d-bf69-6c96ce196451.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154636882-5816b3b8-cf65-4bb9-8106-93c9a4758025.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154637007-661901ac-6f05-44fb-b913-620db4a565fa.png)<br>


**12. C# Program to perform a file comparision**<br>
using System;<br>
using System.IO;<br>

namespace ex14<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("enter the first file path: ");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("enter the second file path: ");<br>
            file2 = Console.ReadLine();<br>
            if(!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("First file does not exist!");<br>
            }<br>
           else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("Second file does not exist!");<br>
            }<br>
            else if(File.ReadAllText(file1)==File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both file contain the same content");<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("Content of file are not same");<br>
            }<br>
            <br>
   }<br>
   }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154635067-d805cd9c-76c0-42c2-bff2-32fb27cb6394.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154635125-b41c4a15-cb33-431a-826c-8e526ba2ca91.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154635349-c83e6091-8b72-4f2a-b962-100547c613bd.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154634783-c273d4c6-77eb-4198-8251-b2f70cf8fee4.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154634965-84d7a2e7-dc2a-4348-877c-90cb2e225948.png)<br>



**13. C# program to Implement IComparable interface.**<br>
using System;<br>
namespace ex17<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>

   Fraction[] a = {<br>
 new Fraction(5,2),<br>
 new Fraction(29,6),<br>
 new Fraction(4,5),<br>
 new Fraction(10,8),<br>
 new Fraction(34,7)<br>
 };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying Fractions: ");<br>
            foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154637579-23b8dacf-5de8-4679-a073-abcda81202d8.png)<br>



**14 c# program to create thread pools.**<br>
using System;<br>
using System.Threading;<br>

namespace ex18<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>

  }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>

   }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for(int i=0;i<2;i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>

   }<br>
            Console.ReadKey();<br>
        
   }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154637919-1c05db93-56bd-4188-9f6e-741e0ad7d1fe.png)<br>



**15. C# program to demostrate error handling using try,catch and finally block**<br>
using System;<br>
namespace ex19<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch(AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException:{0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of finally block is done");<br>
            }<br>
            <br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException:Exception<br>
{<br>
    public AgeIsNegativeException(string message):base(message)<br>
    {<br>

   }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if(age<0)<br>
        {<br>
            throw (new AgeIsNegativeException("age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("age is:{0}", age);<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154638151-631c25eb-770d-43a1-bfd8-12dbd098c717.png)<br>


**16. C# program to generate fibonacci series.**<br>
using System;<br>
public class FibonacciExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n1 = 0, n2 = 1, n3, i, number;<br>
        Console.Write("Enter the number of elements: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1   <br> 
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed v   
        {<br>
            n3 = n1 + n2;<br>
            Console.Write(n3 + " ");<br>
            n1 = n2;<br>
            n2 = n3;<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155657785-2bc1b9c6-fa2f-4a34-a419-24409d61e134.png)<br>


**17. C# program to generate prime numbers.**<br>
using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155659035-ddb1e636-c75d-4c7c-a1e1-48c66c86b52c.png)<br>
![image](https://user-images.githubusercontent.com/97940850/155658911-39bd075e-c7c0-4ac3-90d9-c9e030400fdb.png)<br>


**18. C# program to check a palindrom number or not**<br>
using System;<br>
public class PalindromeExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155659869-5b1b78c0-af9f-4d3c-8270-008043e7a190.png)<br>
![image](https://user-images.githubusercontent.com/97940850/155659980-ff53ed9c-1dee-4251-8ce5-5406a54a51b7.png)<br>


**19. c# program to find a factorial of a number.**<br>
using System;  <br>
  public class FactorialExample  <br>
  {  <br>
     public static void Main(string[] args) <br> 
     {  <br>
       int i,fact=1,number;   <br>   
       Console.Write("Enter any Number: ");   <br>   
       number= int.Parse(Console.ReadLine());     <br>
       for(i=1;i<=number;i++){      <br>
        fact=fact*i;      <br>
     }      <br>
       Console.Write("Factorial of " +number+" is: "+fact);    <br>
     }  <br>
  } <br>
  **OUTPUT**<br>
  ![image](https://user-images.githubusercontent.com/97940850/155661285-d1078b59-4ce7-42fb-925b-0f284606b844.png)<br>


**20. C# Program to check a armstrong number or not.**<br>
using System;  <br>
  public class SumExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  n,sum=0,m;         <br>
       Console.Write("Enter a number: ");     <br> 
       n= int.Parse(Console.ReadLine());     <br>
       while(n>0)      <br>
       {      <br>
        m=n%10;      <br>
        sum=sum+m;      <br>
        n=n/10;      <br>
       }      <br>
       Console.Write("Sum is= "+sum); <br>     
     }  <br>
  }  <br>
  **OUTPUT**<br>
  ![image](https://user-images.githubusercontent.com/97940850/155662154-6136ac80-78ef-4962-8917-0268bc7d6fd9.png)<br>


**21. C# Program to Reverse a number.**<br>
using System;  <br>
  public class ReverseExample <br> 
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  n, reverse=0, rem;          <br> 
       Console.Write("Enter a number: ");    <br>  
       n= int.Parse(Console.ReadLine());   <br>  
       while(n!=0)      <br>
       {      <br>
        rem=n%10;     <br>   
        reverse=reverse*10+rem;      <br>
        n/=10;      <br>
       }      <br>
       Console.Write("Reversed Number: "+reverse);   <br>    
    }  <br>
  }  <br>
  **OUTPUT**<br>
  ![image](https://user-images.githubusercontent.com/97940850/155662699-37d7f14f-efa6-4318-ba57-3e2aafc164ef.png)<br>
  
  
  **22. C# Program to swap two numbers without using third variable.**<br>
  using System;  <br>
  public class SwapExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  a=5, b=10;            <br>
       Console.WriteLine("Before swap a= "+a+" b= "+b);  <br>  
       a=a*b; //a=50 (5*10)      <br>
       b=a/b; //b=5 (50/10)      <br>
       a=a/b; //a=10 (50/5)    <br>
       Console.Write("After swap a= "+a+" b= "+b);     <br>  
     }  <br>
  }   <br>
  **OUTPUT**<br>
  ![image](https://user-images.githubusercontent.com/97940850/155663724-69ed18af-3ba3-424b-8729-741740489632.png)<br>



**WINDOW APPLICATION**<br>
**23. C# Program to Convert Digit to Word.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace EX2<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
<br>
   private void button1_Click(object sender, EventArgs e)<br>
            {<br>
                lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));<br>
                lbl_words.Visible = true;<br>
            }<br>
            public string NumtoWord(long number)<br>
            {<br>
                string word = "";<br>
                if (number == 0)<br>
                {<br>
                    return "Zero";<br>
                }<br>
                if (number < 0)<br>
                {<br>
                    return "Minus" + Math.Abs(number);<br>
                }<br>
                if (number / 10000000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 10000000) + "Corer";<br>
                    number %= 10000000;<br>
                }<br>
   if (number / 100000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 100000) + "Lacs";<br>
                    number %= 100000;<br>
                }<br>
                if (number / 1000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 1000) + "Thousand";<br>
                    number %= 1000;<br>
                }<br>
                if (number / 100 > 0)<br>
                {<br>
                    word += NumtoWord(number / 100) + "Hundred";<br>
                    number %= 100;<br>
                }<br>
                if (number > 0)<br>
                {<br>
                    string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",<br>
                                        "Seven", "Eight", "Nine","Ten", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",<br>
                                           "seventeen", "Eighteen", "Nineteen" };<br>
                    string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",<br>
                                            "Sixty", "Seventy", "Eighty", "Ninety" };<br>
                    if (number < 20)<br>
                    {<br>
                        word += units[number];<br>
                    }<br>
                    else<br>
                    {<br>
                        word += Tens[number / 10];<br>
                        if (number % 10 > 0)<br>
                        {<br>
                            word += units[number % 10];<br>
                        }<br>
                    }<br>
                }<br>
                return word;<br>
            }<br>
          }<br>
    }<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/157811585-b1d9cdcd-2205-478d-8e55-68d194fb60e8.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157811701-fd70946c-b319-4a1c-afaf-51d38b0a5d14.png)<br>

**24.Write a c# program to perform money conversion.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
<br>
namespace money<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
<br>
   private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            {<br>
                label4.Visible = true;<br>
                if (textBox1.Text == "")<br>
                {<br>
                    label4.Text = "Enter the amount";<br>
                }<br>
                else<br>
                {<br>
                    Double convertedamt = Convert.ToDouble(textBox1.Text);<br>
<br>
   if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "USD")<br>
                    {<br>
                        Double a = convertedamt / 74;<br>
                        label4.Text = a + "$";<br>
                    }<br>
<br>
   else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem ==  "SAR")<br>
                    {<br>
                        Double a = convertedamt / 17;<br>
                        label4.Text = a + "SAR";<br>
                    }<br>
<br>
   else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "EUR")<br>
                    {<br>
                        Double a = convertedamt / 11;<br>
                        label4.Text = a + "EUR";<br>
                    }<br>
                    else<br>
                    {<br>
                       label4.Text = "Please Enter the conversion code";<br>
                    }<br>
                }<br>
            }<br>
         }<br>
<br>
   private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            textBox1.Text = "";<br>
            label4.Text = "";<br>
        }<br>
    }<br>
}<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165695780-3f60aebd-5c4d-40cc-afd9-19cbd24b70d3.png)<br>
![image](https://user-images.githubusercontent.com/97940850/165695992-c09f39dd-70ee-4a2b-9eae-4357c8fe1678.png)<br>

**25.C# Program to Perform Reversal, Padding and Trimming Operations on String.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace Ex4<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

   private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString, revstr = "";<br>
            int Length;<br>
            inputString = txtInput.Text;<br>
            Length = inputString.Length - 1;<br>
            while (Length >= 0)<br>
            {<br>
                revstr = revstr + inputString[Length];<br>
                Length--;<br>
            }<br>
            MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
     }<br>

   private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>

   private void button3_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            inputString = inputString.PadLeft(10, '*');<br>
            inputString = inputString.PadRight(15, '*');<br>
            MessageBox.Show("String After Padding : " + inputString, "Result");<br>
        }<br>
    }<br>
}<br>
<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/157820042-fad259a0-c217-4985-8061-ed9917f82b83.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820255-85ec84ed-f8a2-4ce9-939f-e364e778ad3c.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820391-2179174d-8bf5-40fa-b2b9-77a415f3ef50.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820500-e232d52a-8749-4a9d-ae04-f793c46ab17b.png)<br>


**26. C# program to create a progress Bar Control.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>

namespace Ex5<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
        
   private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            backgroundWorker1.WorkerReportsProgress = true;<br>
            backgroundWorker1.RunWorkerAsync();<br>
        }<br>

   private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
        {<br>
            for(int i=1;i<=100;i++)<br>
            {<br>
                Thread.Sleep(50);<br>
                backgroundWorker1.ReportProgress(i);<br>
            }<br>
        }<br>

   private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
        {<br>
            progressBar1.Value = e.ProgressPercentage;<br>
            this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br>
        }<br>
    }<br>
}<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/158744516-374f7b05-839f-4522-b80c-4ff1354355db.png)<br>
![image](https://user-images.githubusercontent.com/97940850/158744620-edb24f3e-44c6-4ce7-8dfe-5f165d0261fb.png)<br>

**27.Create a winform application to create a flat clock.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
<br>
namespace Ex6<br>
{<br>
    public partial class Form1 : Form
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            timer1.Start();<br>
        }<br>
<br>
   private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;//1s<br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
<br>
        }<br>

   private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");<br>
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM<br>
            });<br>
        }<br>
    }<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/158756208-93c72317-fa9d-4067-9d01-5fd5fd85d6ad.png)<br>
![image](https://user-images.githubusercontent.com/97940850/158756416-fd1230af-c26c-4bd5-b88b-2e3f801203ba.png)<br>

**28. C# Program to perform a number guessing game**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace Ex7<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        // Intialising component <br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        Button button1;<br>
        TextBox textBox1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
    public Form1()<br>
        {<br>
            InitializeComponent();<br>
            {<br>
                value = r.Next(100);<br>
                this.Controls.Clear();<br>
                this.BackColor = Color.SkyBlue;<br>
                this.AutoSize = true;<br>
                this.Padding = new Padding(16);<br>
                Label label = new Label();<br>
                label.Text = "Pick a number between 1 and 100";<br>
                label.Bounds = new Rectangle(10, 20, 340, 40);<br>
                label.Font = new Font("Arial", 16);<br>
                textBox1 = new TextBox();<br>
                textBox1.Bounds = new Rectangle(20, 50, 120, 80);<br>
                textBox1.Font = new Font("Arial", 24);<br>
    button1 = new Button();<br>
                button1.Text = " Check Your Guess ";<br>
                button1.Bounds = new Rectangle(160, 50, 120, 40);<br>

   button1.BackColor = Color.LightGray;<br>
                button1.Click += new EventHandler(button1_Click);<br>
                Label label2 = new Label();<br>
                label2.Text = "Low Guess";<br>
                label2.Bounds = new Rectangle(20, 150, 160, 40);<br>
                label2.Font = new Font("Arial", 18);<br>
                richTextBox1 = new RichTextBox();<br>
                richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);<br>
                richTextBox1.Font = new Font("Arial", 16);<br>

   Label label3 = new Label();<br>
                label3.Text = "High Guess";<br>
                label3.Bounds = new Rectangle(180, 150, 160, 40);<br>
                label3.Font = new Font("Arial", 18);<br>
                richTextBox2 = new RichTextBox();<br>
                richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);<br>
                richTextBox2.Font = new Font("Arial", 16);<br>
                label4 = new Label();<br>
                label4.Bounds = new Rectangle(20, 100, 700, 40);<br>
                label4.Font = new Font("Arial", 16);<br>
                this.Controls.Add(label);<br>
                this.Controls.Add(textBox1);<br>
                this.Controls.Add(button1);<br>
                this.Controls.Add(label4);<br>
                this.Controls.Add(label2);<br>
                this.Controls.Add(label3);<br>
                this.Controls.Add(richTextBox1);<br>
                this.Controls.Add(richTextBox2);<br>
            }<br>
        }<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            // Coding of game <br>
            if (textBox1.Text == "")<br>
            {<br>
                return;<br>
            }<br>
            guessnum = Convert.ToInt32(textBox1.Text);<br>
            textBox1.Text = String.Empty;<br>
            if (win >= 0)<br>
            { <br>
            if (guessnum == value)<br>
                {<br>
                    MessageBox.Show("You have guessed the number! \n The number was:  " + value);<br>
                    InitializeComponent();<br>
                }<br>
                else if (guessnum < value)<br>
                {<br>
                    richTextBox1.Text += guessnum + "\n";<br>
                    label4.Text = "wrong Guess and number \n of guesses left are " + (10 - guess);<br>
                }<br>
                else if (guessnum > value)<br>
                {<br>
                    richTextBox2.Text += guessnum + "\n";<br>
                    label4.Text = "wrong Guess and number \n  of guesses left are " + (10 - guess);<br>
                }<br>
                guess++;<br>
                win--;<br>
            }<br>
            if (guess == 11)<br>
            {<br>
                label4.Text = "You loose,Correct Guess is " + value;<br>
            }<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>

   }<br>
  }<br>
}<br>

**OUTPUT***<br>
![image](https://user-images.githubusercontent.com/97940850/160999223-fc15c585-ee5c-42f3-8c90-f38818e6ef44.png)
![image](https://user-images.githubusercontent.com/97940850/160998196-821312f4-51d2-4aad-bd5f-e015a0028272.png)
![image](https://user-images.githubusercontent.com/97940850/160998804-0a59440e-bba5-4981-bd0e-cc1c397d0bf5.png)



**29.C# program to develop an application to create a notepad.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace Notepad<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
        }<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        internal Form1()<br>
        {<br>
            fileName = null;<br>
            initializeComponents();<br>
        }<br>

   void initializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing);<br>
            this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right |<br>
           AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>
            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
    saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
   OpenFileDialog openDlg = new OpenFileDialog();<br>


   if (DialogResult.OK == openDlg.ShowDialog())<br>
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName);<br>
                        this.Text = "My notepad " + fileName;<br>
                    }     break;<br>
            }<br>
        }<br>
        void saveFile()<br>
        {<br>
    if (fileName == null)<br>
            {
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {<br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        
   private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
        }<br>
       }<br>
    }<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/160996633-68b7f69e-35e4-48a0-b605-299df4ff69a7.png)<br>


**30.C# Program to develeop a Binary tree.**<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
using System.Drawing.Drawing2D;<br>

namespace BinaryTree<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private Node root;<br>
    public Form1()<br>
        {<br>
            InitializeComponent();<br>
            this.root = null;<br>
            test();<br>
        }<br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "3";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "2";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "1";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "4";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "7";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "6";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "8";<br>
            btnAdd_Click(btnAdd, null);<br>
        }<br>
    private void btnCreate_Click(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>
    }<br>
<br>
   private void btnAdd_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>
                root = new Node(value);<br>
            else<br>
    {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>

   }<br>
            drawTree();<br>
        }<br>
<br>
   private void btnRemove_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root != null)<br>

   {<br>
                bool status = root.Remove(value, root, ref root);<br>
                if (status == false)<br>
     {<br>
                   MessageBox.Show("the value does not exists");<br>
     }<br>
   }<br>
            drawTree();<br>
        }<br>
   private void btnSearch_Click(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>

   {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
            {<br>
                if (root.Exists(value))<br>
    {<br>
                    msg = "Value found";<br>
                }<br>
                else<br>
    {<br>
                    msg = "Value not found";<br>
    }<br>
<br>
  }<br>
            MessageBox.Show(msg);<br>
        }<br>
        void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
       /* static void Main()<br>
        {<br>
            Application.Run(new BinTreeForm());<br>
        }*/<br>
    }<br>
    class Node<br>
    {<br>
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;<br>
        private static Bitmap nodeBg = new Bitmap(30, 25);<br>
        private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>
                {<br>
                    this.right = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.right.Add(value);<br>
            }<br>
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (right != null)<br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left;<br>
                    if (root == this)<br>
                        root = left;<br>
                }<br>
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                            parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);<br>
            Image lNodeImg = null;<br>
            Image rNodeImg = null;<br>
            int lCenter = 0, rCenter = 0;<br>
    if (this.left != null)<br>
            {<br>
                lNodeImg = left.Draw();<br>
                lSize = lNodeImg.Size;<br>
                this.center = lSize.Width;<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br>
                rSize = rNodeImg.Size;<br>
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height;<br>
            if (maxHeight > 0) maxHeight += 35;<br>
            Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height +<br>
maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
<br>
   Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));<br>
            g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
<br>
string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7,<br>
           nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {<br>
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35);<br>
                var points1 = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 - w/6, y1 + h/3.5f),<br>
 new PointF(x2 + w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2),<br>
 };<br>
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg != null)<br>
            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35);<br>
                x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 + w/6, y1 + h/3.5f),<br>
 new PointF(x2 - w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2)<br>
 };<br>
                g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
            }<br>
            return result;<br>
        }<br>
        public bool Exists(int value)<br>
        {<br>
            bool res = value == this.value;<br>
            if (!res && left != null)<br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        }<br>

    }<br>
}<br>
    <br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/161213365-03aef4dd-42e4-470a-bea9-27761a769ab1.png)<br>

    

