# Franciszek Thomas 2pr

## **Klasa w C++, cz. 2**

**Hermetyzacja danych**

Przykład:

```cpp
class Klasa
{
public:

    . . .

    const int& GetVariable() const
    {
        return m_variable;
    }

    void SetVariable(const int& variable)
    {
        m_variable = variable;
    }

    . . .

private:
    int m_variable;
};
```

Zmienne klasy warto także nazywać `m_[nazwa zmiennej]`, gdzie "m_"  
oznacza że mamy doczynienia ze zmienną która  
jest powiązana z klasą (*ang. **m**ember variable*)

**Dziedziczenie klass**

W C++ klasy mogą dziedziczyć zmienne oraz metody.  
Klasy podstawowe mogą także posiadać metody wirtualne,  
które mogą być nadpisywane przez klasy pochodne.
Klasy które posiadają same "czyste" metody wirtualne (*ang. pure virtual function*) nazywamy interfejsami.  

```cpp
class A
{
public:
    A() = default;
    ~A() = default;

    virtual std::string GetName()
    {
        return "A";
    }
public:
    int m_a;
    int m_b;
};

class B : public A
{
public:
    B() = default;
    ~B() = default;

    std::string GetName() override
    {
        return "B";
    }
};

. . .

A* klasa_a = new A;
A* klasa_b = new B;

klasa_a->GetName(); // A
klasa_b->GetName(); // B
```

Metody klas w C++ to tak naprawdę zwykłe funkcje których pierwszy argument to wskaźnik "this"  
(wskaźnik do bloku pamięci, gdzie przechowywane są zmienne oraz *VMT* klasy)  
Dzięki temu wskaźnikowi metoda klasy klasa ma dostęp do swoich zmiennych.

Metody wirtualne to także zwyczajne funkcje, ale ich adresy  
przechowywane są w tak zwanej "vmt" (*ang. **v**irtual **m**ethod **t**able*).  
