# First message (pt-BR)

Este é o único texto que o agente fala antes de saber com quem está falando.
Ele não pode revelar dívida, valor, credor nem produto.

```
Oi, boa tarde. Aqui é a assistente do {CREDOR}. Falo com {PRIMEIRO_NOME}?
```

## Por que assim

- Abre curto. Ligação de cobrança que começa com parágrafo é desligada.
- Diz de onde é logo, porque esconder gera desconfiança e reclamação.
- Termina em pergunta fechada, que força o turno de fala e confirma o titular.
- Não diz "cobrança" na primeira frase. Diz na segunda, depois da confirmação.

## Variantes para testar

Versão neutra:
```
Oi, boa tarde. Aqui é a assistente do {CREDOR}. Falo com {PRIMEIRO_NOME}?
```

Versão que já sinaliza que é máquina:
```
Oi, boa tarde. Aqui é a assistente virtual do {CREDOR}. Falo com {PRIMEIRO_NOME}?
```

Testar as duas importa: declarar que é um agente muda a taxa de desligamento
nos primeiros cinco segundos, e o número vai nos dois sentidos dependendo do público.

## Segunda fala, após confirmação do titular

```
Perfeito. Estou ligando sobre uma pendência do seu {PRODUTO}, com {DIAS_ATRASO} dias
em atraso. Consegue falar um minuto agora?
```
