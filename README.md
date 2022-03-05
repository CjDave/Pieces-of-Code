# Pieces-of-Code
``` c#
int inp = 645;
int len = inp.ToString().Length;
string[] desc = { "ones", "tens", "hundreds", "thousands", "ten thousands", "hundred thousands", "million", "ten million", "hundred million" };
int div = 1;
for (int i = 0; i < len; i++)
{
  div = div * 10;
  int mun = (inp % div) - (inp % (div / 10));
  Console.WriteLine(mun + " " + desc[i]);
}

``
