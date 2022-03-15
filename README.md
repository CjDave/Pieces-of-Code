# Pieces-of-Code

### Converting a digit to it's tens, hundreds, thousands...
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
### Leetcode Problem [(Integer to Roman)](https://leetcode.com/problems/integer-to-roman/)
```c#
public class Solution {
public string IntToRoman(int num) 
{
    string result = "";
    int len = num.ToString().Length;
    int div = 10;
    int temp;
    while (len > 0)
    {
           temp = (num % div) - (num % (div / 10));
        temp = temp / (div / 10);
        div = div * 10;
        result = conv(temp, (num.ToString().Length-len)) + result;
        len--;
    }
return result;
}
string conv(int i, int p)
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
