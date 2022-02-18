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



















![image](https://user-images.githubusercontent.com/97940850/154633617-d4c0cfbd-1716-4701-a7c4-dcb4baffae82.png)
