# Treća vježba

U okviru treće vježbe radili smo dva izazova gdje smo **implementirali zaštitu integriteta poruke** korištenjem **HMAC** **mehanizma** i utvrđivali **vremensku sekvencu transakcija sa odgovarajućim dionicama**.

Prvi izazov je obuhvaćao **zaštitu integriteta poruke**. Na lokalnom direktoriju smo kreirali tekstualnu datoteku. Nakon toga smo implementirali funkcije za generiranje **MAC** vrijednosti i provjeru validnosti dane poruke. Nakon toga smo pokušali modificirati sadržaj i uvidjeli da **MAC** algoritam detektira promjene.

Drugi izazov smo uradili sami. Prvo smo preuzeli personalizirani izazov koji je sadržavao transakcije dionica.
Danu for-petlju je trebalo modificirati kako bi manualno provjerila sve transakcije.