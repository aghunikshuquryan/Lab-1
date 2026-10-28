1.Class, Random, matrix, set get, private public, constructor
ստեղծել Կլասս որը կպարունակի NxN չափերով մատրիցա
Կլասսում պահել private դաշտեր N, A և B, ամբողջ թվերի համար, և նրանց համար ապահովել {set get} մեթոդները կարճ գրելաձևով,
ստեղծել private FillMatrix անունեով մեթոդ, որը կլրացնի մատրիցայի արժեքները [A, B] միջակայքից պատական թվերով
ստեղծել public ShowMatrix մեթոդը, որը ցույց կարտածի մատրիցայի պարունակությունը
ստեղծել մեթոդ որը կվերադարձնի մատրիցայի կենտ թվերի քանակաը
պարամետրիզացված Կոնստրուկտորով տեղադրել N, A և B դաշտերի արժեքները որից հետո կանչել FillMatrix մեթոդը
ցույց տալ կլասսի ֆունկիոնալությունը Main() մեթոդում
```c#

using System;

class Matrix
{
    private int n;
    private int a;
    private int b;
    private int[,] matrix;

    public int N
    {
        get { return n; }
        set { n = value; }
    }

    public int A
    {
        get { return a; }
        set { a = value; }
    }

    public int B
    {
        get { return b; }
        set { b = value; }
    }

    private void FillMatrix()
    {
        Random rnd = new Random();

        matrix = new int[n, n];

        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                matrix[i, j] = rnd.Next(a, b + 1);
            }
        }
    }

    public void ShowMatrix()
    {
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                Console.Write(matrix[i, j] + "\t");
            }

            Console.WriteLine();
        }
    }

    public int CountOdd()
    {
        int count = 0;

        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < n; j++)
            {
                if (matrix[i, j] % 2 != 0)
                {
                    count++;
                }
            }
        }

        return count;
    }

    public Matrix(int n, int a, int b)
    {
        N = n;
        A = a;
        B = b;

        FillMatrix();
    }
}

class Program
{
    static void Main()
    {
        Matrix m = new Matrix(4, 1, 20);

        Console.WriteLine("Matrix:");
        m.ShowMatrix();

        Console.WriteLine("Odd numbers count: " + m.CountOdd());
    }
}
```
