---
layout: default
---

[Strona główna](/pl)

[Poprzedni rozdział: Zmienne, wyrażenia warunkowe i pętle](/pl/2_language_basics)  
[Następny rozdział: Rekurencja](/pl/4_recursion)

## Funkcje

Funkcje to fragmenty kodu, które mogą być wywołane do wykonania po nazwie. Zobaczmy na przykład poniżej zawierający dwie definicje funkcji.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/33"></iframe>

Po pierwsze, jeśli uruchomisz aplikację, zobaczysz, że nic nie jest rysowane - dzieje się tak, ponieważ kod składa się jedynie z dwóch definicji funkcji i musimy je wywołać, by zostały wykonane. Jak wywołać funkcję? To proste i tak naprawdę już to umiesz! Za każdym razem, kiedy piszesz `move(...)` lub `rotate(...)` lub `up()`/`down()` itd. wywołujesz funkcję. Zatem tutaj byłoby po prostu napisanie `move40andRotate90()` lub `moveAndRotate(40, 90)`.

Jak już zapewne wiesz, czasami dodatkowo do nazwy funkcji czasem można przekazać pewne wartości (nazywane parametrami lub argumentami) w okrągłych nawiasach. To zależy od tego, w jaki sposób zdefiniowana jest funkcja. Zobaczmy na pierwszą definicję funkcji. Zaczyna się od słówka `def`, które oznacza początek definicji funkcji. Następnie mamy nazwę funkcji i następujące po niej puste nawiasy, następnie znak równości i na końcu nawiasy klamrowe otaczające tzw. ciało funkcji, tj. linie kodu, które zostaną wykonane w momencie wywołania funkcji.\

Druga definicja różni się od pierwszej - nawiasy okrągłe zawierają tzw. listę parametrów. Lista ta definiuje, ile wartości powinno być przekazanych do wywołania funkcji i jakiego powinny być typu. Oto kilka podstawowych typów:

* `Int` oznacza liczbę całkowitą,
* `Double` lub `Float` oznacza liczbę rzeczywistą,
* `String` oznacza tekst,
* `Boolean` oznacza wartości logiczne (prawda/fałsz).

W tym przypadku widzimy, że do funkcji `moveAndRotate` powinny zostać przekazane dwa argumenty i oba powinny być całkowite. Teraz zobaczny, w jaki sposób argumenty wykorzystywane są wewnątrz ciała funkcji. Są one po prostu traktowane jak każda inna zmienna w tym zakresie. Jedyną różnicą jest, że jej wartość nie jest zdefiniowana tutaj - będzie ona zależała od wartości przekazanej do funkcji (i przy każdym wywołaniu funkcji wartość ta może być inna). Dokładniej, argumenty traktowane są jako zmienne `val`, więc jeśli mamy parametr nazwany `size`, nie będzie możliwe przypisanie mu innej wartości (jak np. zwiększenie go o 2: `size = size - 2`).

W naszym przykładzie obydwie funkcje miały na celuwykonanie pewnych akcji. Funkcje mogą być jednak używane także, by wykonać pewne obliczenia i zwrócić wynik, który może być dalej użyty w kodzie. Zazwyczaj Scala nie wymaga zdefiniowania typu zwracanego funkcji (co zostało wykorzystane w przykładzie), ale czasami może to być konieczne (patrz następny rozdział - "Rekurencja"), a czasem jest to polecane jako dobra praktyka, dla czytelności kodu. Typ zwracany funkcji definiowany jest między listą parametrów a ciałem funkcji. W przypadku funkcji, które mają wykonać pewne akcje i nie zwracają żadnej wartości, typem zwracanym powinien być `Unit`. Oznacza to, że możemy zmienić definicje w przykładzie, dodając `: Unit` zaraz za listą parametrów, n.p.:

```scala
def moveAndRotate(...): Unit = {
  ...
}
```

Teraz popatrzmy na przykład funkcji, która rzeczywiście zwraca coś istotnego. Pamiętasz funkcję `setColor`? Przyjmuje ona jeden argument typu `Color`, co oznacza, że możemy go również użyć jako typ zwracany funkcji. W Scali zwracana jest wartość ostatniego wyrażenia w ciele funkcji.

```scala
def booleanToColor(b: Boolean): Color = {
  val c = if (b) Color.Red else Color.Green
  c
}
```

Jak widać, do zmiennej `c` przypisujemy czerwony lub zielony kolor (zależnie od wartości argumentu) i zwracamy `c`. Nie ma potrzeby robić tego w ten sposób - równoważnie i bardziej zwięźle można napisać tę funkcję następująco:

```scala
def booleanToColor(b: Boolean): Color = {
  if (b) Color.Red else Color.Green
}
```

### Ćwiczenia:

1. Pobaw się przykadem z definicjami funkcji - wywołaj je, może kilkakrotnie, spróbój przekazać różne wartości parametrów do funkcji, która je przyjmuje.
2. Zdefiniuj funkcję do rysowania kwadratu, przyjmującą jeden parametr - długość boku. Postaraj się jak najbardziej skrócić ciało funkcji (wykorzystaj informacje z sekcji "Pętle" w poprzednim rozdziale). Wykorzystaj napisaną funkcję do narysowania dużego kwadratu z kilkoma mniejszymi w jego wnętrzu. ([&#8594;](/pl/solutions#ex3.2))
3. \* Napisz funkcję rysującą wielokąt foremny. Powinna ona przyjmować dwa argumenty: ilość boków oraz długość boku. ([&#8594;](/pl/solutions#ex3.3))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Strona główna](/pl)

[Poprzedzni rozdział: Zmienne, wyrażenia warunkowe i pętle](/pl/2_language_basics)  
[Następny rozdział: Rekurencja](/pl/4_recursion)