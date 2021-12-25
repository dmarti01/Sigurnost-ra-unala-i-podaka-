# Peta vježba

Tematika pete vježbe je bila vezana za **online** i **offline password guessing**.

Prvo smo radili online password guessing.
Prvi zadatak je bio da **pingamo** lokalni server.
Zatim smo instalirali **nmap** softver za skeniranje portova i skenirali 16 portova.
Nakon toga smo otvorili vlastite direktorije na serveru i zapisivali vlastite ip adrese.
Nakon toga smo otvorili **ssh remote shell**.
Zatim smo instalirali **hydra aplikaciju** koju smo koristili za **online guessing napad**.
Kako bi napad bio uspješan, skinuli smo **online dictionary** i uvezali ga sa hydrom pomoću komande hydra -l martinovic_domagoj -P dictionary/g1/dictionary_online.txt 10.0.15.1 -V -t 4 ssh. Nakon otprilike 50% **brute-force** pokušaja dobili smo željenu lozinku.

Za offline password guessing napad smo koristili **hashcat password cracker**. Ponovo smo koristili dictionary za napadanje lozinki i uvezali ga sa hashcat. Nakon toga smo provjerili je li lozinka dobra ssh logiranjem.