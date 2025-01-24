# Sistema de Alocação de Datashows

Este sistema permite gerenciar a alocação de datashows para salas, verificando sua disponibilidade, alocando e desalocando conforme necessário.

## Funcionalidades

- Verificar disponibilidade de datashows.
- Alocar datashows para salas.
- Desalocar datashows.

## Requisitos

- **SWI-Prolog** ou **SWISH Prolog** (opcional, versão online).

## Como Usar

1. **Verificar a disponibilidade** de um datashow:
   ```prolog
   ?- disponivel(dt1).
   ?- alocada(sl1, dt1).
   ?- desalocar_datashow(dt1).

2. **Exemplo de fluxo completo** de um datashow:
  ```prolog
   % Verificar disponibilidade antes da alocação
   ?- disponivel(dt1);
   O datashow dt1 está disponível.

   % Alocar o datashow
   ?- alocar_datashow(sl1, dt1);
   O datashow dt1 foi alocado para a sala sl1.

   % Verificar disponibilidade após a alocação
   ?- disponivel(dt1);
   O datashow dt1 não está disponível.

   % Desalocar o datashow
   ?- desalocar_datashow(sl1,dt1).
   O datashow dt1 foi desalocado.

3. é possivel alocar e desalocar sequencialmente os datashow com:

    ?- alocar_datashow(Sala, Datashow).
    para desalocar:
    ?- desalocar_datashow(Sala, Datashow).

    Caso nao queira passar um dos parametros a consulta ficaria assim e ocorreria para todos que estiverem alocados:

    ?- desalocar_datashow(Sala,_).

4.Verificar todos os datashow disponivéis 
    ?- disponivel(Datashow).