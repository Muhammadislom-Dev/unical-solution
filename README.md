# unical-solution

#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main()
{
  string s;
  cin >> s;
  
  vector<int> vec1 = {'{','[','('};
  vector<int> vec2 = {'}',']',')'};
  
  vector<int> vec;
  
  for (auto i : s)
  {
    if (find(vec1.begin(), vec1.end(), (int)i) != vec1.end()) vec.push_back(i);
    else
    {
      if (i == vec2[find(vec1.begin(), vec1.end(), vec.back()) - vec1.begin()]) vec.erase(vec.end() - 1);
      else break;
    }
  }
  
  cout << ((vec.empty()) ? "YES" : "NO");
  
  return 0;
}

Ushbu algoritm C++ dasturlash tilida tuzilgan.
