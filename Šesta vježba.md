# Šesta vježba

Šesta vježba bila je osmišljena kao upoznavanje s osnovnim postuplkom upravljanja korisničkim računima na **Linuxu**.

Prvi zadatak je bio dodavanje novog korisnika naredbom **sudo adduser “user”**. Nakon toga smo se ulogirali kao taj korisnik naredbom **su - “user** i kreirali još jedan korisnčki račun.

U drugom zadatku smo provjeravali prava pristupa određenim datotrekama tako što smo se ulogirali kao prethodno napravljeni novi korisnik i kreirali neku datoteku. 

Zatim smo izlistavali informacije o direktoriju i datoteci pomoću naredbi **ls -l** ili **getfacl**. Nakon toga je trebalo oduzeti pravo pristupa dotičnoj datoteci pomoću naredbe **chmod**. To smo onda testirali logiranjem na druge korisnike i pristupanjem datoteci.

Na kraju svega zadatak je bio kreirati Python skriptu i izvršiti je putem raznih korisnika. S time smo i zaključili ovu vježbu.