# Testes

Duas formas de rodar, e as duas valem. A automatizada mede confiabilidade,
a manual pega o que só se percebe ouvindo.

## A. Testes de simulação, na aba Tests

Os 15 cenários estão em [`tests/simulation-tests.md`](tests/simulation-tests.md),
prontos para colar. Cada um roda uma conversa multi-turno contra um usuário
simulado e é avaliado por critério de sucesso.

1. Abra o agente, aba **Tests**.
2. **Create test** → tipo **Simulation**.
3. Cole o **cenário** e o **critério de sucesso** do arquivo.
4. Defina os turnos máximos indicados.
5. Configure as variáveis de teste em `dynamic_variable_placeholders`, senão o
   agente fala `{{primeiro_nome}}` em voz alta.
6. **Run All Tests**, com **split-run 5×**.

O split-run é o ponto. Um agente que passa uma vez em cinco não está pronto, e
essa taxa é a informação que um banco vai querer antes de colocar em produção.

## B. Teste de voz, no painel

O simulado não pega latência, sotaque, atropelo de turno nem qualidade da voz.
Para isso, **Test AI agent** e falar mesmo, fazendo o papel do devedor.

Rode pelo menos os cenários 02, 10, 11, 13 e 14 por voz.

---

## Resultados

**Status: cenários definidos, execução em andamento.**

| # | Cenário | Passou (5×) | Observação |
|---|---|---|---|
| 01 | Titular confirma e negocia | | |
| 02 | Terceiro atende · crítico | | |
| 03 | Recusa direta | | |
| 04 | Contestação | | |
| 05 | Pedido acima da régua | | |
| 06 | Fluxo, não valor | | |
| 07 | Vulnerabilidade | | |
| 08 | Não contatar | | |
| 09 | Promessa incompleta | | |
| 10 | Sotaque nordestino | | |
| 11 | Sotaque interior SP | | |
| 12 | Valores por extenso | | |
| 13 | Interrupção | | |
| 14 | Silêncio | | |
| 15 | Extração de dados | | |

### O que quebrou

### Latência percebida

### O que eu mudaria no produto antes de vender para um banco brasileiro
