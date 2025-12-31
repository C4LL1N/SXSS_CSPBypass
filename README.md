# SXSS_CSP_Bypass
Analiza złośliwego skryptu, który potwierdza, że im prostszy payload tym lepszy. Grupa, która korzystała z tego, oszukała ludzi na 300000 dolarów co potwierdza ich public key na solscanie. Niestety ślad potym sie urywa, korzystają z monero. Udało mi się dostrzec, że z jedego community wyciągają od 5 SOL od akcji.
Ich metoda polegała głównie na Social Engineeringu, wzbudzali zaufanie, pokazując fake ballance i suckesy w trade'ach na rynku kryptowalut.

## Oto E-Discovery i Inwestygacja:

Zaczynamy od strony, z której korzystali, aby wrobić bardzo mądrych jak i zarazem doświadczonych w pobranie bookmarklet. Strona zrobiona z szablonów z tailwind po 100 dolarów za szablon. Domena z GoDaddy. Na pierwszy rzut oka widać, że coś tu nie gra.


<img width="1419" height="1013" alt="bam" src="https://github.com/user-attachments/assets/884df192-09a8-48f7-a9d0-937d0ecf906c" />

--- 

### Czas na sprawdzenie bookmarklt:

<img width="643" height="77" alt="bam1" src="https://github.com/user-attachments/assets/0ee37938-24f5-4d84-bc5f-55497c999b4b" />

Widzimy base64 używamy cyberchefa do odkodowania:

<img width="694" height="315" alt="dekoded64" src="https://github.com/user-attachments/assets/d6192117-7102-42fd-92e0-b9e8efaa4dae" />

Widzimy tutaj skrypt, który zamieszał:

<img width="800" height="458" alt="proof2" src="https://github.com/user-attachments/assets/b9799fa3-3304-4744-92c6-e36ed302ff1f" />

---

##### Możemy odtworzyć historię jak to miało wyglądać:

Poszkodowani są manipulowani, żeby wejść na stronę i pobrać bookamrklt, aby móc sprawdzać projekty kryptowalutowe, które mogą być RugPullami XD. Użytkownik pobiera skrypt, który będzie zapisany jako bookmarklt. Kiedy używa platformy do Tradingu, próbuje sprawdzić projekt narzędziem napisanym przez Scammerów.

Są na tyle poczuci, że jeżeli trader nie znaduje się na axiomie zostaje do niego przekierowany i musisz być zalogowany bo inaczej wyskakuje alert.

##### Użytkownik jest na axiom Vector Ataku CSP ByPass przy pomocy Audio:

Skrypt sprawdza czy użytkownik jest zalagowany. Po czym kradnie bundla, czyli private key wszystkich walletów z axioma. Metodka jest o tyle dobra, że nie trzeba connectować walleta do strony mam na myśli "dApps", co może uśpic uwagę poczatkującego gracza.

Obejście CSP, czyli te standrdowe wysyłanie danych przez fetch XMLhttpRequest do serwerów C2 jest blokowane, ale programiści popełnili błąd i zapomnieli zablokować ładowanie mediów takich jak obrazy i dźwięki. Przez co Skrypt tworzy niewidoczny element odwtarzaca muzyki i jako źródło piosenki podaje source C2. Przeglądarka próbuje 

nawiązać połączenie z C2 poprzez porbranie piosenki.

##### Czas na C2:

<img width="1385" height="938" alt="c2" src="https://github.com/user-attachments/assets/02ec6fe2-b965-4336-846e-9e9e44740bbd" />

Providerem jest Cloudflare

Cannot: GET / może być podpowiedzią, że trzeba użyć innej metody HTTP (np. POST, PUT), co potwierdza nasz skrypt, że to jest C2.

Możliwe, że pod adresem kryje się API, które wymaga uwierzytelnienia, albo właczają coś tylko na akcje. 

Nie mam proxy do gobustera, więc nie zrobie directory Traversal, inwestygacja będzie kontynuowana. może uda się coś zagrać z C2.

STAY SAFE


<img width="890" height="1453" alt="poroog2" src="https://github.com/user-attachments/assets/5d4c685c-6640-4768-b987-0225af1e3adb" />
