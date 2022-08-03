---
title: Info
layout: page
permalink: /info
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Witaj

Witaj na kanale [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }}) . Ten stream korzysta z moda [Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) aby zapewnić interakcję między twórcą, a widzami. Jest tutaj wiele rzeczy które mogą wydawać się skomplikowane nawet dla bardziej doświadczonych użytkowników, ale ten krótki przewodnik pomoże ci ogarnąć wszystko.

## Czym jest Twitch Toolkit?

Twitch Toolkit jest modem stworzonym przez hodlhodl który pozwala widzom wpływać na rozgrywkę na wiele różnych sposobów. Najbardziej wyróżniającym się sposobem jest sklep - [SKLEP]({{- "/" | relative_url -}}), który pozwala Ci kupować rzeczy, które mają pomóc streamerowi w rozgrywce. W zależności od zakupu rzeczy te pojawią się w grze lub w pewien sposób wpłyną na rozgrywkę. Innym sposobem w jaki widz może wpływać na rozgrywkę są ankiety wywoływane przez mod. Wybory których będziesz dokonywać w ankiecie są uzależnione od tego, które opcje w modzie są włączone.

## Jak dołączyć do koloni?
Aby dołączyć do rozgrywki skorzystaj z którejś z poniższych komend:

- `!joinqueue` - dołączasz do losowania o miejsce w koloni
- `!buy pawn` - z miejsca dołączasz do koloni
- `!buy prisoner` - twój kolonista dołącza do koloni jako więzień i musi zostać przekabacony, aby brać udział w życiu koloni

## Czym są monety?

Monety są walutą w modzie. Możesz wyświetlić stan swoich monet korzystając z komendy `{{ bal }}`. 

{% if utils == true %}
Po wpisaniu komendy bal może wyświetlić Ci się parę dodatkowych emotek. W takim przypadku poniżej znajduje się opis tego co dane emotki oznaczają:

- 💰 oznacza ilość monet którą obecnie posiadasz.
- ⚖ oznacza twój obecny poziom karmy.
- 📈 oznacza ilość monet którą zyskasz w momencie kiedy mod będzie nagradzał widzów monetami.
- 📉 oznacza ilość monet którą stracisz w momencie kiedy mod będzie nagradzał widzów monetami.

{% endif %}


{%- if lootboxes == true -%}
Dostaniesz wiadomość od bota jeśli otrzymasz lootboxa. Możesz otworzyć lootboxa używając komendy`!openlootbox`. Ilość lootboxów które posiadasz możesz sprawdzić korzystając z komendy `!lootboxes`. Codziennie dostaniesz nowego lootboxa. AKTUALNIE NIEAKTYWNE, PSUJE MOCNO BALANS!
{%- endif -%}


<br/>
## Czym jest Karma?

Karma jest systemem w modzie który próbuje ograniczać ilość negatywnych wydarzeń, które widz może zrzucić streamerowi na głowę w jednym momencie. Ten system działa poprzez modyfikowanie przychodu który widz dostaje w momencie rozdawania monet przez mod. To oznacza że im mniejszą masz karmę, tym mniej monet dostaniesz. 

## W jaki sposób używać Twitch Toolkit?

Możesz używać Twitch Toolkit na wiele sposobów -- najczęściej korzystasz z niego poprzez komendy - [KOMENDY]({{- "/commands" | relative_url -}}). Jedną z ważniejszych komend jest komenda `{{- buy -}}` która pozwala na kupowanie rzeczy ze sklepu. Inną godną napomnienia komendą jest komenda `!mypawn`, która pozwala Tobie na zobaczenie informacji o swoim koloniście. Nie opiszemy tutaj każej z komend, ale większość z nich powinna sama z nazwy mówić Wam o swojej funkcji albo mieć opis tego co robi na stronie Komendy - [KOMENDY]({{- "/commands" | relative_url -}}) .


{%- if puppeteer -%}
<br/>
## Czym jest Puppeteer?

Lalkarz - [Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) jest modem stworzonym przez Brrainz który pozwala widzowi na bezpośrednie sterowanie jego kolonistami, a także wyświetla w graficzny sposób informacje o koloniście. Przekierowuje niektóre odpowiedzi z Twitch Toolkit na swoją stronę w celu uporządkowania chatu. Jeżeli jesteś zalogowany jako Lalkarz i zastanawiasz się dlaczego bot Ci nie odpowiada, powinieneś najpierw sprawdzić zakładkę `TT` (Twitch Toolkit)  na  stronie.
{%- endif -%}
