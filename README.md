# Agente de cobrança em português do Brasil, no ElevenAgents

Um agente de voz que conduz negociação de dívida em pt-BR, construído para
testar o ElevenAgents no caso de uso e no idioma que eu conheço.

Não é um produto. É um teste com propósito: descobrir onde a plataforma
funciona e onde ela quebra no mercado brasileiro de recuperação de crédito.

## Por que cobrança

A inadimplência no Brasil bateu recorde em julho de 2026: **83,9 milhões de
pessoas negativadas** devendo **R$ 586,4 bilhões**, mais 9 milhões de empresas
com R$ 229,9 bilhões (Serasa). No sistema financeiro, a inadimplência chegou a
**4,7%**, também recorde (Banco Central).

Desse estoque, a parte que um agente de voz consegue trabalhar é o crédito sem
garantia: cerca de **R$ 244 bilhões em atraso**, dois terços de tudo que está
vencido no SFN. Imóvel, veículo e rural se resolvem por retomada ou judicial,
não por telefone.

É um caso de uso onde a conversa realmente decide o resultado, e onde a régua
de conduta é apertada. Bom lugar para testar um agente.

## O que tem aqui

```
agent/system-prompt.md    prompt do agente, com régua de desconto e limites de conduta
agent/first-message.md    abertura e a segunda fala, com o racional de cada escolha
agent/config.json         configuração exportada do agente
TESTES.md                 15 cenários de teste e o que quebrou em cada um
```

## Configuração no ElevenAgents

1. Dashboard, novo agente, **Blank template**.
2. Aba **Agent**, seção **Additional Languages**: adicionar **Portuguese (Brazil)**.
   Ao adicionar um idioma além do inglês, a plataforma passa a usar o modelo
   **v2.5 Multilingual**.
3. Aba **Agent**: colar **System prompt** e **First message**.
   A primeira mensagem é traduzida automaticamente por LLM. Reescrevi na mão,
   porque a tradução automática perdeu o registro de cobrança.
4. Aba **Voice**: voz em português do Brasil, feminina, ritmo médio.
5. **Test AI agent** para rodar os cenários de TESTES.md.

## Decisões de projeto que valem explicação

**A primeira mensagem não pode revelar a dívida.** Se quem atende não é o titular,
qualquer menção a valor ou credor é vazamento de dado pessoal. O prompt trata isso
como regra inegociável, não como preferência.

**A régua de desconto é sequencial e o agente não pode pular etapas.** Um agente que
oferece o desconto máximo na primeira objeção destrói margem mais rápido que um
humano mal treinado, porque ele faz isso em escala e sem cansar.

**Promessa de pagamento só conta com valor, data e forma.** Sem os três, é interesse,
não promessa. É a diferença entre um indicador que prevê caixa e um que não prevê nada.

**Conduta segue o artigo 42 do CDC.** Sem constrangimento, sem ameaça, sem exposição
ao ridículo. A janela de contato de 8h às 20h é uma restrição operacional conservadora,
e varia por estado e por política do credor.

## Contexto

Construído por Ricardo Wodianer de Mello, São Paulo. Vinte anos vendendo tecnologia
de crédito, risco e recuperação para bancos brasileiros: Serasa Experian, Provenir,
TransUnion, NeuroTech, Capgemini.
