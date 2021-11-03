# Druga Vježba

U sklopu druge vježbe smo dobili personalizirani **crypto** izazov u vidu dešifriranja ciphertexta *pogađanjem* enkripcijskih ključeva.

Najprije smo u Command Promptu iskoristili komandu **pip install cryptography** i zatim pokrenuli **Python**, te testirali neke njegove komande i poneke kriptografske komande.

Nakon toga smo morali dešifrirati svoj crypto izazov koristeći sustav **Fernet**. Sa lokalnog servera smo preuzeli vlastiti crypto izazov nakon dešifriranja. Izazov je bio enkriptiran **ključevima ograničene entropije - 22 bita**.

Zadatak je bio modificirati kod datoteke **brute_force.py**.
Finalni kod je izgledao ovako:

```jsx
import base64
from cryptography.hazmat.primitives import hashes
from cryptography.fernet import Fernet

def hash(input):
    if not isinstance(input, bytes):
        input = input.encode()

    digest = hashes.Hash(hashes.SHA256())
    digest.update(input)
    hash = digest.finalize()

    return hash.hex()

def test_png(header):
    if header.startswith(b"\211PNG\r\n\032\n"):
        return True

def brute_force():
    filename = "3f7699d1bc4ee53a3e8f24bfd2577a150260f938f45b8d6a538819129263bd13.encrypted"
    # Reading from a file
    with open(filename, "rb") as file:
        ciphertext = file.read()

    ctr = 0
    while True:
        key_bytes = ctr.to_bytes(32, "big")
        key = base64.urlsafe_b64encode(key_bytes)

        if not (ctr + 1) % 1000:
            print(f"[*] Keys tested: {ctr + 1:,}", end="\r")

        try:    
            plaintext = Fernet(key).decrypt(ciphertext)
            
            header = plaintext[:32]
            if test_png(header):
                print(f"[+] KEY FOUND: {key}")
                # Writing to a file
                with open("BINGO.png", "wb") as file:
                    file.write(plaintext)         
                break

        except Exception:
            pass
            
        ctr += 1

if __name__ == "__main__":
    # hash_value = hash("cagalj_mario")
    # print(hash_value)
    brute_force()
```