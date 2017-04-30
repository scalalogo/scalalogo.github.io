---
layout: default
---

[Strona główna](/pl)

[Poprzedni rozdział: Funkcje](/pl/3_functions)

## Rekurencja

Pamiętaj, że ten rozdział jest o wiele bardziej zaawansowany od poprzednich, więc nie przejmuj się, jeśli będzie on dla Ciebie trudny.

Rekurencja występuje, gdy funkcja wywołuje samą siebie w swoim ciele. Zacznijmy od przykładu niezwiązanego z rysowaniem. Napiszemy rekurencyjną funkcję do liczenia sumy liczb całkowitych od `0` do podanego `n`. Pamiętaj, że robimy tylko po to, by pomóc Ci zrozumieć pojęcie rekurencji, bo takie obliczenia mogą być (i normalnie powinny być) wykonane bez rekurencji. Możesz napisać taką funkcję jako ćwiczenie, a poniżej możesz zobaczyć rekurencyjną wersję. Należy również wspomnieć, że w przypadku funkcji rekurencyjnych, Scala wymaga jawnego podania typu zwracanego.

```scala
def sum(n: Int): Int = {
  if (n <= 0) 0 else n + sum(n - 1)
}
```

Załóżmy, że wywołujemy tę funkcję z argumentem o wartości `2`. Wówczas zostałaby ona obliczona następująco:

```
sum(2) = 2 + sum(1) = 2 + 1 + sum(0) = 2 + 1 + 0 = 3
```

Bardzo istotne jest, że rekurencja musi się kiedyś skończyć. Oznacza to, że nie możemy wywoływać funkcji rekurencyjny cały czas, bezwarunkowo. W powyższym przykładzie jeśli argument wynosi 0, zwracamy po prostu 0. Tylko dla dodatnich agrumentów rzeczywiście tworzymy rekurencję (z argumentem mniejszym o 1), by obliczyć sumę liczb od `0` do `n - 1` i zwrócić ją powiększoną o `n`.

Teraz spróbujmy użyć prostej rekurencji do rysowania. Ponownie narysujemy kwadratową spiralę, ale tym razem zaczniemy od najdłuższego boku.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/36"></iframe>

Rekurencja w grafice jest często używana do tworzenia [fraktali](https://pl.wikipedia.org/wiki/Fraktal). Poniżej możesz zobaczyć przykład rekurencyjnego drzewa:

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/38"></iframe>

A to jest [paproć Barnsleya](https://pl.wikipedia.org/wiki/Papro%C4%87_Barnsleya):

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/41"></iframe>

### Ćwiczenia

1. Narysuj [dywan Sierpińskiego](https://pl.wikipedia.org/wiki/Dywan_Sierpi%C5%84skiego). ([&#8594;](/pl/solutions#ex4.1))
2. Narysuj [trójkąt Sierpińskiego](https://pl.wikipedia.org/wiki/Tr%C3%B3jk%C4%85t_Sierpi%C5%84skiego). ([&#8594;](/pl/solutions#ex4.2))
3. Narysuj [krzywą Kocha](https://pl.wikipedia.org/wiki/Krzywa_Kocha). ([&#8594;](/pl/solutions#ex4.3))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Strona główna](/pl)

[Poprzedni rozdział: Funkcje](/pl/3_functions)