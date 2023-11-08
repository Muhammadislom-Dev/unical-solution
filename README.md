# unical-solution

#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main()
{
  string s;
  cin >> s; // consoledan qavslar ketma ketligini o'qish
  
  vector<int> vec1 = {'{','[','('}; // ochilgan qavslar
  vector<int> vec2 = {'}',']',')'}; // yopilgan qavslar
  
  vector<int> vec; // qavslarni o'rnini tekshirish uchun massiv
  
  for (auto i : s) // kiritilgan qavslar bo'yicha birma bir aylanish
  {
    if (find(vec1.begin(), vec1.end(), (int)i) != vec1.end()) vec.push_back(i); // agar tanlangan qavs ochuvchi bo'lsa, massivga qo'shish
    else
    {
      if (i == vec2[find(vec1.begin(), vec1.end(), vec.back()) - vec1.begin()]) vec.erase(vec.end() - 1); // aks holda tanlangan qavsning ochuvchisini massivning oxirgi elementi bilan tekshirish, agar teng bo'lsa massivdan ochuvchi qavsni o'chirish
      else break; // aks holda massivni elementini qoldirgan holda siklni to'xtatish
    }
  }
  
  cout << ((vec.empty()) ? "YES" : "NO"); // agar massiv bo'sh bo'lsa "YES" aks holda "NO" chiqarish
  
  return 0;
}
Ushbu algoritm C++ dasturlash tilida tuzilgan.
