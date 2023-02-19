# Franciszek Thomas 2pr

## **Słownik** (*ang*. Dictionary)

Słownik to struktura danych która opiera się na parach klucz - wartośc.  
Klucz jest zwykle ciągiem znaków, ale klucz może być też jakimkolwiek innym typem danych.  
Podstawowo słownik ma trzy operacje:

- insert
- search
- delete

**`insert`** umieszcza parę klucz - wartość w słowniku.  
**`search`** wyszukuje wartość po danym kluczu  
**`delete`** usuwa wartość o danym kluczu  

Słownik jako struktura danych ma bardzo wiele zastosowań, na przykład:

- Prosta baza danych
- Plik konfiguracyjny
- Lista wartości

Typowa implementacja słownika to tablica mieszająca, gdyż jest to jedna z efektywniejszych metod.  
przykładem implementacji słownika jako tablicy mieszającej (*ang*. hash table)  
może być klasa **`std::unordered_map`** i **`std::map`** w bibliotece standardowej języka C++.  

Zalety słowników to głownie niska złożoność czasowa operacji "szukania" wartości,  
oraz poniekąd prostota w implementacji tej struktury danych.  

Przykład użycia słownika w C++:

```cpp
std::unordered_map<const char*, float> values =
{
    { "one",    1.23f },
    { "two",    4.56f },
    { "three",  7.89f },
    { "four",   0.01f },
    { "five",   9.16f },
    { "six",    2.27f },
    { "seven",  2.00f },
};

. . .

values["one"] = 20.0f;
values["two"] = 30.0f;

. . .

for (const auto& it : values)
{
    std::cout << it.first << ": " << it.second << '\n';
}
```
