---
layout: default
---

[Strona główna](/pl)

[Poprzedni rozdział: Wprowadzenie](/pl/1_introduction)  
[Następny rozdział: Funkcje](/pl/3_functions)

## Zmienne

W przykładzie w poprzednim rozdziale, zawsze poruszaliśmy żółwia o 60 kroków. Teraz wyobraź sobie, że chcesz wykonać ten sam rysune, ale dwa razy większy. Trzeba by zmienić te 60 na 120 w każdym miejscu osobno. Zamiast tego, można wprowadzić zmienną: `val size = 60`, a następnie użyć jej we wszystkich miejscach następująco: `move(size)`. W ten sposób zmiana rozmiaru rysunku wymagałaby zmiany tylko jednej linii: napisania `val size = 120` zamiast `val size = 60`.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/26"></iframe>

Innym sposobem tworzenia zmiennej jest `var size = 60`, który różni się od poprzedniego pierwszym słowem - mamy `var` zamiast `val`. Jeśli zmienna zadeklarowana jest jako `var`, oznacza to, że jej wartość może zostać zmieniona w trakcie wykonania programu:

```scala
var size = 20
(...)
size = 30
```

To nie byłoby możliwe, gdyby zmienna była stworzona jako `val`.

Możemy chcieć, żeby nowa wartość zmiennej zależała od jej poprzedniej wartości. Na przykład `size = size + 10` zwiększyłoby rozmiar zmienner `size` o dziesięć. To samo można krócej zapisać jako `size += 10`. Możesz również użyć `*` do mnożenia zamiast dodawania, `-` do odejmowania lub `/` do dzielenia.

### Przykład

Narysujmy początek kwadratowej spirali. Zaczniemy od odcinka długości 10 i obrotu o 90 stopni i powtórzymy to kilkukrotnie, zwiększając rozmiar każdego kolenego odcinka o 10.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/50"></iframe>

## Wyrażenia warunkowe

Czasem możemy chcieć wykonać jakąś akcję zależnie od pewnego warunku. W takiej sytuacji przydatne są wyrażenia warunkowe. Warunki to wyrażenia logiczne - w naszym przypadku mogą one opierać się na pewnych właściwościach zmiennych liczbowych takich jak na przykład:

* `n > 5` - prawdziwy, gdy zmienna `n` jest większa niż 5,
* `n >= 5` - prawdziwy, gdy zmienna `n` jest większa lub równa 5,
* `n < 5` - prawdziwy, gdy zmienna `n` jest mniejsza niż 5,
* `n <= 5` - prawdziwy, gdy zmienna `n` jest mniejsza lub równa 5,
* `n == 5` - prawdziwy, gdy zmienna `n` ma wartość 5,
* `n != 5` - prawdziwy, gdy zmienna `n` ma wartość inną niż 5,
* `n % 2 == 0` - prawdziwy, gdy zmienna `n` jest parzysta,
* `n % 2 != 0` - prawdziwy, gdy zmienna `n` jest nieparzysta.

Możemy również chcieć sprawdzić więcej niż jeden warunek:

* jeśli chcemy, żeby wszystkie podane warunki wyły prawdziwe, to powinny one być połączone za pomocą `&&` - np: `a == 1 && b == 2 && c == 3`,
* jeśli chcemy, żeby przynajmniej jeden warunek był prawdziwy, łączymy je za pomocą `||` - np.: `a == 1 || b == 2 || c == 3`.

Najprostszym przykładem może być sytuacja, w której chcemy wykonać jakiś kod tylko wtedy, jeśli pewien warunek jest prawdziwy.

```scala
if (warunek) {
  //kod zawarty tutaj będzie wykonany tylko, jeśli podany warunek jest prawdziwy
}
```

Możemy również chciećwykonać pewien kod, jeśli podany warunek jest fałszywy. Wówczas kod wygląda następująco:

```scala
if (warunek) {
  //kod zawarty tutaj będzie wykonany tylko, jeśli podany warunek jest prawdziwy
} else {
  //kod zawarty tutaj będzie wykonany tylko, jeśli podany warunek jest fałszywy
}
```

Inną możliwością jest, że jeśli pierwszy warunek jest fałszywy to chcemy sprawdzić inny. I jeśli ten drugi też jest fałszywy, chcemy sprawdzić jeszcze kolejny itd.. Można to osiągnąć, pisząc następujący kod:

```scala
if (warunek1) {
  //kod A
} else if (warunek2) {
  //kod B
} else if (warunek3) {
  //kod C
} else {
  //kod D
}
```

W powyższym przykładzie:

* jeśli `warunek1` jest prawdziwy, wykonany zostanie "kod A",
* jeśli `warunek1` jest fałszywy ale `warunek2` jest prawdziwy, wykonany zostanie "kod B",
* jeśli zarówno `warunek1` jak i `warunek2` są fałszywe ale `warunek3` jest prawdziwy, zostanie wykonany "kod C",
* jeśli `warunek1`, `warunek2` i `warunek3` wszystkie są fałszywe, zostanie wykonany "kod D".

Warto również wspomnieć, że ostatni fragment: `else {...}` jest opcjonalny - nie musimy go pisać, jeśli nie chcemy wykonywać żadnego kodu w przypadku, gdy żaden warunek nie jest spełniony. Wówczas kod wyglądałby następująco:

```scala
if (warunek1) {
  //kod A
} else if (warunek2) {
  //kod B
} else if (warunek3) {
  //kod C
}
```

Użyjmy wyrażeń warunkowych w poniższym przykładzie do stworzenia trójkąta - zielonego, jeśli jego bok jest dłuższy niż 100, czerwonego w przeciwnym przypadku. Spróbuj zmienić wartość `size` i zobacz rezultaty.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/47"></iframe>

Można również w zwięzły sposób uzależnić wartość przypisywaną do zmiennej od jakiegoś warunku: `val s = if (n >= 0) n else -n`. Ten fragment kodu przypisuje zmiennej `s` wartość `n`, jeśli `n` jest nieujemne, i liczbę przeciwną (`-n`) jeśli `n` jest ujemne - tak czy inaczej, wartość `s` nie będzie ujemna.

Tę opcję wykorzystamy w poniższym przykładzie - bardzo podobnym do poprzedniego.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/28"></iframe>

## Pętle

Bardzo często chcemy wykonać ten sam (lub bardzo podobny) fragment kodu kilkakrotnie. Najprostszy sposób, by to osiągnąć, jest następujący:

```scala
repeat(10) {
  //tutaj wpisz kod
}
```

Kod wpisany w nawiasach klamrowych zostanie powtórzony 10 razy. Oczywiście liczba 10 została tu wybrana przypadkowo. W jej miejscu możesz także użyć zmiennej lub wyrażenia o wartości całkowitej.

```scala
val N = 5
repeat(N) {
  //kod A
}
repeat(N + 2) {
  //kod B
}
```

W powyższym przykładzie "kod A" będzie powtórzony 5 razy a "kod B" będzie powtórzony 5 + 2 = 7 razy.

Konstrukcja `repeat` pozwala jedynie na proste powtórzenia. Moglibyśmy jej użyć w naszym pszykładzie rysującym kwadratową spiralę, ale lepiej będzie użyć pętli `for`.

```scala
for(i <- 1 to 10) {
  move(i * 10)
  rotate(90)
}
```

W tym przykładzie kod w nawiasach klamrowych zostanie wykonany 10 razy. Dlaczego? Ze względu na `i <- 1 to 10` - oznacza to, że podczas każdego kolejnego wykonania kodu w pętli zmienna `i` będzie miała inną wartość: zaczynając od 1, potem, 2, 3, itd., aż do 10, co razem daje 10 razy! W rezultacie narysujemy dziesięć krawędzi spirali - o długościach odpowiednio 10, 20, 30, ..., 100.

W Scali istnieje wiele innych form pętli `for`, jednakże nie będziemy się tu zagłębiać w ich dalsze szczegóły.

Kolejną podobną konstrukcją jest pętla `while`.

```scala
while(warunek) {
  //jakiś kod
}
//inny kod
```

W miejscu `warunku` może być dowolne wyrażenie logiczne (patrz: sekcja "Wyrażenia warunkowe"). Wykonanie przebiega następująco:

 1. wyliczana jest wartość warunku ("prawda lub "fałsz")  
  1.a. jeśli warunek jest fałszywy, wykonywany jest kod w nawiasach klamrowych i wykonanie przechodzi do "innego kodu"  
  1.b. jeśli warunek jest prawdziwy, wykonany zostaje kod w klamrowych nawiasach, a następnie **przechodzimy z powrotem do punktu 1.** (ewaluacji warunku)

W poniższym przykładzie możesz zobaczyć, jak pętla `while` została użyta to narysowania kwadratowej spirali do momentu, gdy długość boku przekroczyła 150.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/29"></iframe>

### Ćwiczenia:

1. Stwórz podobne trójkątne spirale, zaczynając rysowanie od najdłuższego odcinka. Wykorzystaj do tego:

* konstrukcję `repeat` ([&#8594;](/pl/solutions#ex2.1.a)) 
* pętlę `for` ([&#8594;](/pl/solutions#ex2.1.b))
* pętlę `while` ([&#8594;](/pl/solutions#ex2.1.c))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Strona główna](/pl)

[Poprzedni rozdział: Wprowadzenie](/pl/1_introduction)  
[Następny rozdział: Funkcje](/pl/3_functions)