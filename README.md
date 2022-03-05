# Pieces-of-Code
``` c#
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

``
