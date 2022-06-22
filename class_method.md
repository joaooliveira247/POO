# Métodos de classe

Um método de classe é aquele o qual pode ser acessado diretamente pela classe, sem a necessidade de ser instânciado.

- Pode acessar e modificar atributos de classe.
- Pode modificar um estado de classe que se aplicaria a todas as instâncias da classe.
- Não pode acessar atributos de instancia.

    > **_Observação_:**
    >
    > Todo método ou atributo com "self" seria de instância.

Para usar um método de classe devemos utilizar um decorador:

```python3
@classmethod
```

- acessando e/ou modificando um atributo:

```python3
from typing import Optional


class Personagem:
    mana = 200

    def __init__(self, name: str, pais: str) -> None:
        self.name = name
        self.pais = pais

    @classmethod
    def pegar_mana(cls, mana: Optional[int] = None) -> int:
        if mana:
            cls.mana = mana
        return cls.mana
```

`out:`

Acessando:

![attribute_out](/pictures/metodos_de_classe/attributes_out.png)

Modificando:

![attribute_modify_out](/pictures/metodos_de_classe/attributes_modify_out.png)

- Modificando o estado de uma classe:

```python3
from typing import Optional


class Personagem:
    mana = 200

    def __init__(self, name: str, pais: str) -> None:
        self.name = name
        self.pais = pais

    @classmethod
    def registrar_personagem(cls, nome: str, pais: str, mana: int):
        cls.mana = mana
        return cls(nome, pais)
```

`out:`

![state_class](/pictures/metodos_de_classe/state_class.png)