# c-sharp-practice
//1. Заданы a и b, вывести a + b

using System;
class HelloWorld {
  static void Main() {
      Console.Write("a is ");
      int a = Convert.ToInt32(Console.ReadLine());
      Console.Write("b is ");
      int b = Convert.ToInt32(Console.ReadLine());
      Console.Write("Result is {0}",a+b);
  }
}

//<--------------
//2. Вывести сумму n целых чисел

using System;
class HelloWorld {
  static void Main() {
    Console.Write("n is ");
    int n = Convert.ToInt32(Console.ReadLine());
    int summ = 0;
    for(int i=0;i<n;i++) summ += Convert.ToInt32(Console.ReadLine());
    Console.Write("summ is {0}", summ);
  }
}
//<--------------
//3. Альтернированной суммой заданной последовательности n чисел a1,a2,...an называется число s=a1-a2+a3-a4+.... В альтернированной сумме знаки слагаемых чередуются, альтернация начинается со знака +. По заданной последовательности целых чисел выведите её альтернированную сумму.

using System;
class HelloWorld {
  static void Main() {
    Console.Write("n is ");
    int n = Convert.ToInt32(Console.ReadLine());
    int summ = 0;
    int status = 1;
    for(int i=0;i<n;i++) {
        if(status>0){
            summ += Convert.ToInt32(Console.ReadLine());
            status = -status;}
        else{
            summ -= Convert.ToInt32(Console.ReadLine());
            status = -status;
        }
    }
    Console.Write("summ is {0}", summ);
  }
}
//<--------------
//4. Задан номер года y. Ваша задача вывести 1, если год високосный, и вывести 0, если нет. Год является високосным, если он кратен 4 и при этом не кратен 100, либо кратен 400.

using System;
class HelloWorld {
  static void Main() {
    Console.Write("year is ");
    int year = Convert.ToInt32(Console.ReadLine());
    if(year%4==0 && (year%100!=0 || year%400==0)) Console.Write("yes");
    else Console.Write("no");
  }
}
//<--------------
//5. Заданы n целых чисел. Вывести индекс первого из минимальных элементов последовательности. Элементы последовательности занумерованы от 1 слева направо.

using System;
class HelloWorld {
  static void Main() {
    Console.Write("n is "); int n = Convert.ToInt32(Console.ReadLine());
    int[] s = new int[n]; int index = -1, minel = 1000000;
    for(int i=0;i<n;i++) {
        s[i] = Convert.ToInt32(Console.ReadLine());
        if(s[i]<minel){
            minel = s[i]; index = i;
        }
    }
    Console.WriteLine("____");
    Console.Write(index+1);
  }
}
//<--------------
//6. Задана длина = n сантиметров. Перевести её в футы и дюймы так, чтобы количество футов было максимально. Ответ должен быть целочисленным, округленным к ближайшему значению, содержащему целое число дюёмов. 1 дюйм = 3 см, 1 фут = 12 дюймов.

using System;
class HelloWorld {
  static void Main() {
      Console.Write("cm "); double n = Convert.ToDouble(Console.ReadLine());
      Console.WriteLine("= {0} feet", Math.Round(n/36));
      Console.Write("= {0} inches", Math.Round(n/36*12));
  }
}
//<--------------
//7. Напишите программу, которая определяет на сколько нулей оканчивается двоичная запись заданного целого числа n

using System;
class HelloWorld {
  static void Main() {
    Console.Write("n is ");
    int n = Convert.ToInt32(Console.ReadLine());
    int count = 0;
    while(n%2==0){
        count+=1;
        n/=2;
    }
    Console.Write("{0} нулей(-ля)(-ль)",count);
  }
}

//<--------------
//8. Задана грузоподъемность грузовика. На него последовательно грузятся предметы массами a1, a2, an..., где ai - масса i-го груза. Если при погрузве очередного предмета рабочие замечают, что в случае завершения процесса вес погруженных предметоа превысит грузоподъёмность, то погрзука этого предмета не осущесмтвляется. Вывести количество предметов, которые будут погружены в соответствии с алгоритмом выше и их суммарную массу.

using System;
class HelloWorld {
  static void Main() {
    Console.Write("max mass is "); int maxmass = Convert.ToInt32(Console.ReadLine());
    Console.Write("n is "); int n = Convert.ToInt32(Console.ReadLine());
    int[] s = new int[n];
    int mass = 0, count = 0;
    
    for(int i=0;i<n;i++) {
        Console.Write("Груз: ");
        s[i] = Convert.ToInt32(Console.ReadLine());
        if(mass+s[i]<=maxmass){
            mass+=s[i];
            count+=1;
        }
    }
    Console.Write("Поместилось {0} шт товара, на массу {1} т", count, mass);
  }
}
//<--------------
//9. Задана последовательность n целых чисел. Вывести сумму всех её элементов, стоящих на позициях, которые являются степенями двойки (1, 2, 4, 8, 16, 32 и т.д.)

using System;
class HelloWorld {
  static void Main() {
    Console.Write("n is "); int n = Convert.ToInt32(Console.ReadLine());
    int summ = 0, fig = 1;
    int[] s = new int[n];
    
    for(int i=0;i<n;i++){
        s[i] = Convert.ToInt32(Console.ReadLine());
        if(i==fig){
            summ+=s[i]; fig*=2;
        }
    }
    Console.Write("Result is {0}", summ);
  }
}
//<--------------
//10. Пока оба данных числа строго положительны, надо из большего числа вычесть меньшее. Результатом работы является большее число после окончания описанной серии вычитаний или 0, если обы часла в конце равны 0. Программа должна вывести количество вычитаний при работе такого алгоритма и результат его работы.

using System;
class HelloWorld {
  static void Main() {
    Console.Write("a is "); int a = Convert.ToInt32(Console.ReadLine());
    Console.Write("b is "); int b = Convert.ToInt32(Console.ReadLine());
    int c = Math.Abs(a-b);
    
    while(a>0&&b>0){
        
        a=Math.Min(a,b);b=c;
        c = Math.Abs(a-b);
        Console.WriteLine("a = {0}, b = {1}, c = {2}",a,b,c);
    }
    Console.WriteLine("_");
    Console.WriteLine(c);
  }
}
//<--------------
