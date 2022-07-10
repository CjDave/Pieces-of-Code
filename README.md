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
---

### My solution to [(Integer to Roman LeetCode)](https://leetcode.com/problems/integer-to-roman/)
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

---

### Python bot to spam text from a text file 
 ```python
import pyautogui
from time import sleep

sleep(10)
file = open('text')
for word in file:
    for two in word.split():
        sleep(1)
        pyautogui.write(two)
        pyautogui.press("enter")

```
Add a text file with a bunch of words and you'll be good to go</br>
<b> Idea gotten from [(Tiktok: @izzacode)](https://www.tiktok.com/@izzacodes/video/6860325937406364933?is_from_webapp=1&sender_device=pc&web_id=7078764212050986502)

---    
    
### Creating/Running C# files in VScode
To create a new  file
  ```
dotnet new console -o myApp
  ```
Shortcut for running C# 
> Install [(Code Runner)](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner) 

> Navigate to File-> preference-> Settings -> \\In the search bar type "run in terminal"\\ OR Ctrl+  -> 
> \\click on the check button\\ "Code-runner: Run In Terminal"-> 
>
> Click on the icon beside the run to open the settings/json file 
> OR  
> Open settings(Ctrl+) and search for "Code-runner: Executed Map" and click on Edit in "settings.json"
>    
> Type in "code-runner.executorMap"    
> A list should appear, find "csharp" and replace "scriptcs" with ' "csharp": "cd $dir && dotnet run $fileName"'

This is a written version of the [(video Tutorial)](https://www.youtube.com/watch?v=CO4BGZOuUkM&t=428s)

### Line Separator(XAML)
 ```XAML
<!--Line Separetor-->
<BoxView HeightRequest="1" BackgroundColor="Gray" HorizontalOptions="FillAndExpand" />
```

### My solution to [(LongestCommonPrefix Leetcode)](https://leetcode.com/problems/longest-common-prefix/)
```c#
public class Solution {
    public string LongestCommonPrefix(string[] strs) {
            int length = strs.Length;
            string answer = "";
            string temp;
            int currLngth, ansLngth;
            if (length > 0)
            {
                answer = strs[0];
                for (int i = 1; i < length; i++)
                {
                    string curr = strs[i];
                    if (answer != curr)
                    {
                        currLngth = curr.Length;
                        ansLngth = answer.Length;
                        answer = ansLngth > currLngth ? answer.Substring(0, currLngth) : answer;
                        int p = 0;
                        ansLngth = answer.Length;
                        temp = "";
                        while (p < ansLngth && answer[p] == curr[p])
                        {
                            temp = temp + answer[p];
                            p++;
                        }
                        answer = temp;
                    }

                }
            }
            return answer;
    }
}
```
### My solution to [(Remove Nth Node From End of List)](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
```c# ListNode one, two;
            two = head;
            if (head != null && head.next != null)
            {
                for (int i = 0; i < n - 1; i++)
                {
                    two = two.next;
                }
                one = head;
                if (two.next == null)
                {
                    head = head.next;
                }
                else
                {
                    two = two.next;
                    while (two.next != null)
                    {
                        two = two.next;
                        one = one.next;
                    }
                    one.next = one.next.next;
                }
            }
            else
            {
                head = null;
            }

            return head;
```
---


