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
**22. C# Program to Convert Digit to Word.**<br>
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

**22.C# Program to Perform Reversal, Padding and Trimming Operations on String.**<br>
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Ex4
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

   private void button1_Click(object sender, EventArgs e)
        {
            string inputString, revstr = "";
            int Length;
            inputString = txtInput.Text;
            Length = inputString.Length - 1;
            while (Length >= 0)
            {
                revstr = revstr + inputString[Length];
                Length--;
            }
            MessageBox.Show("Reverse String Is : " + revstr, "Result");
     }

   private void button2_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");
        }

   private void button3_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            inputString = inputString.PadLeft(10, '*');
            inputString = inputString.PadRight(15, '*');
            MessageBox.Show("String After Padding : " + inputString, "Result");
        }
    }
}

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/157820042-fad259a0-c217-4985-8061-ed9917f82b83.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820255-85ec84ed-f8a2-4ce9-939f-e364e778ad3c.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820391-2179174d-8bf5-40fa-b2b9-77a415f3ef50.png)<br>
![image](https://user-images.githubusercontent.com/97940850/157820500-e232d52a-8749-4a9d-ae04-f793c46ab17b.png)<br>



