# Sistema de Atendimento Hospitalar

Simula a triagem do Hospital Campo Real usando três estruturas de dados lineares implementadas manualmente 

## Como compilar e rodar

```
g++ -std=c++17 -Wall -o atendimento atendimento_template.cpp
./atendimento
```

O código compila sem warnings e sem vazamentos de memória (verificado com `-fsanitize=address,undefined`).

## Estruturas

| Requisito | Estrutura | Operações |
|-----------|-----------|-----------|
| R1 | Fila de pacientes (FIFO, ponteiros `frente` e `tras`) | `enqueue`, `dequeue`, `frente_peek`, `tamanho` |
| R2 | Histórico de atendimentos (pilha, LIFO) | `push`, `pop`, `peek` |
| R3 | Lista de médicos de plantão (lista encadeada) | `adicionarMedico`, `chamarMedico`, `percorrer` |
| R4 | Relatório final | `imprimirHistorico`, que usa uma pilha auxiliar para não destruir o histórico |

## Funcionamento

1. Os médicos são cadastrados na lista, na ordem de disponibilidade.
2. Os pacientes entram no final da fila.
3. Para cada atendimento, o paciente da frente da fila é atendido pelo primeiro médico da lista.
4. O atendimento é empilhado no histórico, e o médico volta ao final da lista.
5. O relatório imprime os atendimentos do mais recente ao mais antigo e mantém o histórico intacto.


## Squad

Nome do squad: Biluzada

Integrantes: Eduardo Pepes Pankievicz