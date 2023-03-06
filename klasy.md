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
    
    void MetodaA(int* argument); // metody klasy
    int MetodaB();
private:
    int a; // prywatna zmienna
    int b;
};
```

Konstruktor klasy jest wywoływany przy tworzeniu obiektu klasy.  
Destruktor klasy jest wywoływany przed zniszczeniem (usunięciem) klasy z pamięci. 
