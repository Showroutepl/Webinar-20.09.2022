# Webinar - 20.09.2022
Materiały do webinaru w ramach cyklu Władcy Sieci

# Topologia

![Topologia](Lab.png)

# Scenariusz
Poniżej proponowany scenariusz wykonania ćwiczeń. Konfigurację wykonujmy tylko na routerach C1-1 i C1-2, nie dotykamy routerów ISP

1) Konfigurujemy sąsiedztwo C-2 do ISP2-1 i poleceniem network dodajemy trasę pomiędzy C1-1 i  C1-2
2) Dodajemy nowe trasy przez redystrybucje static routes na C-2 
3) Konfigurujemy OSPF między C-1 i C-2 i dodajemy redystrybucję z OSPF
4) Konfigurujemy iBGP między C1-1 i C1-2
5) Dodajemy hasło na sesji iBGP
6) Konfigurujemy styk C-1 i ISP2
7) Konfigurujemy AS64499 by nie był to AS tranzytowy
8) Konfigurujemy AS64499, aby ruch do 10.44.44.0/30 w ISP3 szedł przez ISP1, do pozostałych przez ISP2
9) Konfigurujemy AS64499, aby ruch do 10.0.0.0/24 z ISP3 wychodził przez łącze na C-1
10) Konfigurujemy styk C-2 do ISP2-2
11) Konfigurujemy AS64499, aby ruch do 10.44.45.0/24 preferował styk C2 i ISP2-2, pozostałe prefiksy styk z C-2 i ISP2-1
12) Konfigurujemy C-1 w taki sposób by rozgłaszało prefiks 10.44.46.0/24 do ISP1, ale ISP1 nie rozgłaszało go dalej poza swój AS



# Narzędzia potrzebne każdemu adminowi pracującemu z BGP 🧰
__(podobne narzędzia pojawiają się co jakiś czas w naszym [newsletterze](https://showroute.pl/netprasowka))__

https://lg.twelve99.net/ - looking glass operatora Tier 1 (taki który nie płaci za dostęp do Internetu). Mamy dostęp do prawie wszystkich węzłów sieci. Od Europy poprzez Azję aż do obu Ameryk. Cały Internet.<br />
https://lg.atman.pl/ - looking glass polskiego operatora usług biznesowych i data center.<br />
http://lg.tpnet.pl/ - looking glass naszego operatora krajowego.<br />
http://lg.netia.pl/ - looking glass drugiego naszego operatora krajowego. Oprócz looking glass jest też możliwość sprawdzenia przepustowości łącza poprzez pobranie pliku 10MB, 50MB, 100MB i 500MB. Przydaje się i jest w miarę wiarygodne, gdy masz usługę od Netia.<br />
http://lg.retn.net - looking glass przydatny do sprawdzania co się dzieje z naszymi prefiksami na terenie państw CIS/WNP.<br />
https://lg.he.net - looking glass od HE. Duża liczba PoP i wyniki pokazywane w formie surowej (bez tabelek i “ozdobników” graficznych)<br />


https://rpki-validator.ripe.net/ui/ - walidator od RIPE. Działa na oprogramowaniu Routinator, najpopularniejszy obecnie walidator w Internecie.<br />
https://rpki.cloudflare.com/ - walidator od Cloudflare. Oprócz samej opcji sprawdzenia ROA dostarcza również informacje statystyczne dotyczące RPKI i BGP.<br />
https://rpki-monitor.antd.nist.gov/ - walidator od NIST. Podobnie jak walidator od Cloudflare zawiera dane statystyczne, ale ma podział na operatorów i historię.<br />

https://redirector.googlevideo.com/report_mapping - z którego cacha Google właśnie korzystasz. Skąd Twoi klienci oglądają filmy z YouTube. <br />
http://whatismyip.akamai.com/advanced - z którego cacha sieci CDN Akamai właśnie korzystasz. <br />
https://bgp.he.net/ - narzędzie udostępniające informację o prefiksach i AS, które jest rogłaszają.<br />


# Hej to jeszcze nie koniec. Pozostańmy w kontakcie.  👋

Dołącz do newslettera Showroute.pl<br />
Co tydzień dostaniesz mail z 5 linkami wraz z krótkim opisem do treści, związanymi z siecią, ciekawych wpisów, narzędzi, ofert pracy, analizy bieżących wydarzeń w sieci.  

Zapisz się już teraz na https://showroute.pl/netprasowka/
