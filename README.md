# boas-praticas-software

Atividade prática da Aula 6 de **Manutenção e Configuração de Software** (Normas de Configuração e Boas Práticas), realizada individualmente por **Théo da Silva Sá**.

O objetivo foi analisar um pequeno sistema em Java que calcula a média de um aluno, melhorar sua organização e legibilidade aplicando boas práticas, e registrar todas as alterações com Git: commit do código original, branch de melhorias, Pull Request e merge na `main`.

## Questão final

### 1. Qual era o principal problema do código original?
O principal problema era a legibilidade. As variáveis tinham nomes de uma letra (`n`, `a`, `b`, `c`), que não dizem o que guardam, e toda a lógica estava concentrada no método `main`. O valor `6` da média mínima também aparecia solto no meio do código, sem explicar o que significava. O sistema funcionava, mas quem precisasse dar manutenção teria que ler linha por linha para entender o que cada parte fazia.

### 2. Quais melhorias você realizou?
- Renomeei as variáveis para nomes descritivos: `nomeAluno`, `primeiraNota`, `segundaNota` e `media`.
- Dividi o código em métodos com responsabilidades específicas: `calcularMedia`, `verificarSituacao` e `exibirResultado`.
- Substituí o número `6` pela constante `MEDIA_MINIMA_APROVACAO`.
- Padronizei os nomes (camelCase para variáveis e métodos, PascalCase para a classe e maiúsculas para constantes), a indentação e a separação dos blocos com linhas em branco.
- Mantive exatamente a mesma saída do programa original, garantindo que a refatoração melhorou a organização sem alterar o comportamento do sistema.

### 3. Como a modularização facilitou a organização do código?
Com a modularização, cada método passou a ter uma única responsabilidade, e o `main` apenas coordena as etapas: calcular, verificar e exibir. Isso deixa o código mais fácil de ler e de alterar. Por exemplo, se a regra de aprovação mudar, basta alterar o método `verificarSituacao` ou a constante, sem mexer no cálculo nem na exibição. Os métodos também podem ser reutilizados e testados separadamente.

### 4. Como o Git ajudou a controlar as alterações realizadas no sistema?
O Git registrou cada etapa do trabalho. O primeiro commit guarda o código original, que pode ser recuperado a qualquer momento. As melhorias foram feitas em uma branch separada (`melhoria-boas-praticas`), sem afetar a versão principal. Depois, o Pull Request permitiu revisar as diferenças entre o código antigo e o novo antes do merge na `main`. Assim, fica registrado o que mudou, quando mudou e por quê, o que é exatamente a rastreabilidade estudada nas aulas anteriores.

## Como executar
```bash
cd src
javac Sistema.java
java Sistema
```