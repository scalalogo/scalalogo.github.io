---
layout: default
---

[Strona główna](/pl)

[Następny rozdział: Zmienne, wyrażenia warunkowe i pętle](/pl/2_language_basics)

## Wprowadzenie

Zabawa polega na tym, że mamy "żółwia", które może poruszać się po powierzchni, rysując linie w różnych kolorach i kierunkach. Najpierw zobaczmy, jak wyglądają podstawowe akcje dostępne w aplikacji.

* `move(steps)` porusza żółwia o określoną liczbę kroków. Jeśli liczba kroków jest ujemna, żółw porusza się do tyłu.
* `rotate(angle)` obraca żółwia o podany kąt (w stopniach, dodatnie wartości traktowane są zgodnie z ruchem wskazówek zegara). Na przykład: obrót w prawo o kąt prosty można osiągnąć za pomocą `rotate(90)`, taki sam obrót w lewo to `rotate(-90)` lub `rotate(270)`, natomiast zmiana kierunku ruchu na przeciwny to `rotate(180)` lub `rotate(-180)`.
* `up()` podnosi żółwia do góry. Jeśli żółw jest podniesiony, to nie rysuje linii poruszając się.
* `down()` opuszcza żółwia na dół, tak że może on ponownie rysować linie.
* `show()` sprawia, że żółw jest widoczny.
* `hide()` ukrywa żółwia. Widoczność żółwia nie wpływa w żaden sposób na rysowanie.
* `setColor(color)` zmienia kolor linii rysowanych przez żółwia. Możesz użyc gotowych kolorów
(<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: white; border: 1px solid; display: inline-block;"></span> _White_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: silver; border: 1px solid; display: inline-block;"></span> _Silver_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: gray; border: 1px solid; display: inline-block;"></span> _Gray_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: black; border: 1px solid; display: inline-block;"></span> _Black_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: red; border: 1px solid; display: inline-block;"></span> _Red_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: maroon; border: 1px solid; display: inline-block;"></span> _Maroon_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: yellow; border: 1px solid; display: inline-block;"></span> _Yellow_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: olive; border: 1px solid; display: inline-block;"></span> _Olive_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: lime; border: 1px solid; display: inline-block;"></span> _Lime_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: green; border: 1px solid; display: inline-block;"></span> _Green_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: aqua; border: 1px solid; display: inline-block;"></span> _Aqua_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: teal; border: 1px solid; display: inline-block;"></span> _Teal_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: blue; border: 1px solid; display: inline-block;"></span> _Blue_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: navy; border: 1px solid; display: inline-block;"></span> _Navy_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: fuchsia; border: 1px solid; display: inline-block;"></span> _Fuchsia_,</span>
<span style="white-space:nowrap"><span style="height: 10px; width: 10px; background-color: purple; border: 1px solid; display: inline-block;"></span> _Purple_)</span>
lub stworzyć swój własny. Aby użyć gotowego koloru, po prostu napisz `setColor(Color.Blue)`. Swój własny kolor możesz stworzyć w następujący sposób: `setColor(Color(30, 40, 50))`, gdzie 30, 40 and 50 oznaczają odpowiednio wkład czerwonego, zielonego i niebiesiego, w zakresie od 0 do 255 (jest to tak zwany model koloru RGB, więcej informacji na ten temat znajdziesz [tutaj](https://pl.wikipedia.org/wiki/RGB).
* `setInterval(interval)` reguluje, jak długo trwa pojedyncza akcja.
* `write(something)` może być używane do celów testowych. Spowoduje pokazanie tekstowej reprezentacji tego, co zostanie przekazane jako `something`, poniżej przycisków do zarządzania.

Dodatkowo, każda linia zaczynająca się od `//` to tzw. komentarz - nie jest ona traktowana jako kod ani wykonywana.

### Przykład

Powiedzmy, że chcemy narysować sześciokąt foremny, ale w szczególny sposób - rysujemy tylko co drugi bok i każdy w innym kolorze.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/23"></iframe>

### Ćwiczenia:

1. Narysuj ośmiokąt foremny w podobny sposób (tylko co drugi bok i każdy w innym kolorze). Wskazówka: Konieczna będzie zmiana konta obrotu! ([&#8594;](/pl/solutions#ex1.1))
2. Draw a star pentagon. ([&#8594;](/pl/solutions#ex1.2))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Strona głóna](/pl)

[Następny rozdział: Zmienne, wyrażenia warunkowe i pętle](/pl/2_language_basics)