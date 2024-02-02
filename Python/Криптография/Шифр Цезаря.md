Наиболее простой из всех шифров. Принцип шифрования заключен в ключе-позиции по алфавиту

Код:
```python
class CaesarCipher:  
    @staticmethod  
    def decrypt(word: str, n: int) -> str:  
        final = ''  
        word = word.lower()  
        for letter in word:  
            final += chr((ord(letter) + n - 65) % 26 + 65)  
        return final  
  
    @staticmethod  
    def encrypt(word: str, n: int) -> str:  
        final = ''  
        word = word.lower()  
        for letter in word:  
            final += chr((ord(letter) - n - 65) % 26 + 65)  
        return final

```
