# Pieces-of-Code
```c#
int inp = 64500;
int len = inp.ToString().Length;
string[] desc = { "ones", "tens", "hundreds", "thousands", "ten thousands", "hundred thousands", "million", "ten million", "hundred million" };
int div = 1;
int ldiv;
for (int i = 0; i < len; i++)
{
    ldiv=div;
    div = div * 10;

    int mun = (inp % div) - (inp % ldiv);
    Console.Write(mun + " " + desc[i]+"\t");
    Console.Write(mun/ldiv + " " + desc[i]+"\n");

}

```

```c#
    static void Main(string[] args)
        {
            int input = 33;

            string result = "";
            int len = input.ToString().Length;
            int div = 10;
            int divl;
            int temp;
            for (int i = 0; i < len; i++)
            {
                divl = div / 10;
                temp = (input % div) - (input % divl);
                temp = temp / divl;
                div = div * 10;
                result = conv(temp, i) + result;
            }
            Console.WriteLine(result);
        }
        static string conv(int i, int p)
        {
            string[,] roman = new string[,]{ {"","I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"},
                                             {"","X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"}, // tens
                                             {"","C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"}, // hundreds
                                             {"","M", "MM", "MMM","MMMM","V̅","V̅M","V̅MM","V̅MMM","I̅X̅"}
                                             };
            return roman[p, i];
        }
    }

```
