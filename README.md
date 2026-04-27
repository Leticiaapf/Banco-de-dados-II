# Banco-de-dados-II
📘 UNIDADE 1 - Álgebra Relacional
A álgebra relacional é uma linguagem formal e procedimental, ou seja, o usuário define uma sequência de operações que o sistema deve executar para obter o resultado desejado no banco de dados.

📌 Terminologia do modelo relacional
Tupla: Linhas
Atributo: coluna (campo)
Relação: tabela em si
Domínio: é o tipo de dado que define quais valores podem aparecer em cada coluna (atributo).

A álgebra relacional ganhou destaque após o modelo relacional proposto por Edgar F. Codd em 1970, servindo como base para linguagens como o SQL.

⚙️ Operações fundamentais

Existem 6 operações fundamentais na álgebra relacional:

Seleção
Projeção
Produto cartesiano
União
Diferença
Renomear

Essas operações são usadas para manipular dados e sempre geram uma nova tabela (relação) como resultado.

🔄 Funcionamento
Uma relação:
operação(REL1)
REL1 → REL2

Duas relações:
operação(REL1, REL2)
REL1, REL2 → REL3

👉 Resumo: conjunto de operações para consultar e transformar dados, gerando sempre uma nova tabela.

Seleção (σ)

Realiza a seleção de tuplas que satisfazem determinada condição.

Exemplos:
σ Nome = “Renata” (Pessoas)
σ id > 123 (Pessoas)
σ id > 123 ^ id < 789 (Pessoas)
σ nome = “Giullia” v nome = “Juan” (Pessoas)

obs: ^ = AND
     v = OR

Projeção (π)

Permite gerar novas relações selecionando atributos específicos.

Exemplos:  π nome (Alunos)
           π matrícula, nome (σ sexo = ‘M’) (Alunos) 

           Produto Cartesiano

Combina todas as linhas de duas tabelas.

Colunas = soma das colunas
Linhas = multiplicação das linhas
Exemplo:

Se A (3 colunas, 2 linhas) e B (2 colunas, 3 linhas):

5 colunas
6 linhas

👉 Todas as combinações possíveis entre as tabelas.
Exemplo com Alunos e Cursos
π nome, sexo, curso (σ Alunos.curso = Cursos.id) (Alunos x Cursos)

Etapas:

Produto cartesiano → 16 tuplas
Seleção → correspondência entre curso e id
Projeção → apenas nome, sexo e curso
➕ União (U)

Junta linhas de duas tabelas sem duplicidade.

Mesma quantidade de colunas obrigatória
Linhas no máximo = soma das duas
R1 U R2 = R2 U R1
➖ Diferença (-)

Retorna o que está na primeira tabela e não na segunda.

Requer tabelas compatíveis
Não é comutativa
R1 - R2 ≠ R2 - R1
🔁 Interseção (∩)

Retorna apenas os dados comuns entre duas tabelas.

Sem duplicidade
Tabelas devem ser compatíveis
R1 ∩ R2
🧠 Resumo Geral
Seleção → filtra linhas
Projeção → seleciona colunas
Produto cartesiano → combina tabelas
União → junta sem repetir
Diferença → remove comuns
Interseção → pega apenas comuns
