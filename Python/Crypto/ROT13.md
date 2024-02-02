ROT13 - частный случай шифра Цезаря с позицией 13. 
Является взаимным шифром (или обладает свойство инволюции - два последовательных применения восстанавливают первоначальный текст)

Код:
 ```python
 class ROT13:  
    @staticmethod  
    def decrypt(word: str) -> str:  
        final = ''  
        for symbol in word:  
            final += chr(ord(symbol) % 26 + 65)  
        return final
```