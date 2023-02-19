# Franciszek Thomas 2pr

## **Klasa w C++**

**Podstawowe informacje**

Klasa w C++ może być interpretowana jako struktura z funkcjami (metodami).  
Klasy posiadają trzy poziomy dostępu do zmiennych i metod:

- public
- private
- protected

**`public`** metody i zmienne są "ogólno" dostępne
**`private`** metody i zmienne są widoczne tylko dla klasy
**`protected`** metody i zmienne są widoczne dla klasy podstawowej jak i dla klasy pochodnej.  

Składnia klasy w C++:

```cpp
class JakasKlasa
{
public:
    JakasKlasa(); // konstruktor klasy
    ~JakasKlasa(); // destruktor klasy
private:
    int a; // prywatna zmienna
    int b;
};
```

Dobrą praktyką jest, aby deklarować zmienne klasy jako prywatne,  
a jak potrzebujemy aby zmienna była widoczna dla użytkownika dodajemy do klasy metody  
`Get[nazwa zmiennej]` oraz `Set[nazwa zmiennej]`.  

Warto także nazywać zmienne klasy `m_[nazwa zmiennej]`, gdzie "m_"  
oznacza że mamy doczynienia ze zmienną która  
jest powiązana z klasą (*ang. **m**ember variable*)

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

**Dziedzictwo klass**

W C++ klasy mogą dziedziczyć zmienne oraz metody.  
Klasy podstawowe moga także posiadać metody wirtualne,  
które mogą być nadpisywane przez klasy pochodne.
Klasy które posiadają same metody wirtualne nazywamy interfejsami.  

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

Metody klas w C++ to tak naprawdę zwykłe funkcje których pierwszy argument to wskaźnik "this" (wskaźnik do klasy) dzięki któremu klasa ma dostęp do swoich zmiennych.

Metody wirtualne to także zwyczajne funkcje, ale ich adresy  
przechowywane są w tak zwanej "vmt" (*ang. **v**irtual **m**ethod **t**able*).  

Konstruktor klasy jest wywoływany przy tworzeniu obiektu klasy.  
Destruktor klasy jest wywoływany przed zniszczeniem (usunięciem) klasy z pamięci.