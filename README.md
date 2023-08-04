# MoneyCent

***Money Cent***
```
stock FormatMoney(amount, delimiter[2]=".", comma[2]=",") // first type data on stock variable amount just has a integer.
// make stock for head new fungsition formating how money cent read with coma and dot
{
  #define MAX_MONEY_String 16
  new MoneyAtString[MAX_MONEY_String];
  format(MoneyAtString, MAX_MONEY_String, "%d", amount);
  new l = strlen(MoneyAtString);
  if (amount < 0) // - value (minus)
  {
    if (l > 2) strins(MoneyAtString,delimiter,l-2); // cent
    if (l > 5) strins(MoneyAtString,comma,l-5); // tousand
    if (l > 8) strins(MoneyAtString,comma,l-8); // million
  }
  else
  {//1000000 , so strins is adding new chacter like (,) or (.)
    if (l > 2) strins(MoneyAtString,delimiter,l-2);
    if (l > 5) strins(MoneyAtString,comma,l-5);
    if (l > 9) strins(MoneyAtString,comma,l-8);
  }
  if (l <= 2) format(MoneyAtString,sizeof( MoneyAtString),"00,%s",MoneyAtString);
  return MoneyAtString; // this value integer has been changed to string.
}
```
****C: Putu Suhartawan****

**Cara pakenya tinggal di ubah %i jadi %s soalnya cent dan comma tidak termasuk ke Integer**
