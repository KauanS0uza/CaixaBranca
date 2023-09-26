# CaixaBranca

## Descrição

Esse é um código pré enviado por mim, e fiz a seguinte analise com o Teste de caixa branca

## Erros no código

1.Erro no Nome do Driver MySQL:
Você está tentando carregar o driver do MySQL usando a classe "com.mysql.Driver.Manager", mas a forma correta de carregar o driver é "com.mysql.cj.jdbc.Driver".

2.Manipulação inadequada:
No bloco try-catch em conectarBD(), você está capturando exceções, mas não está fazendo nada dentro do bloco catch.

3.Vulnerabilidade a SQL Injection:
O código concatena diretamente os valores login e senha na consulta SQL. Isso torna seu aplicativo vulnerável a ataques de SQL.

## Pontos de observação no teste de caixa branca:

1.A DOCUMENTAÇÃO FOI DESCRITA NO CÓDIGO?
Não, o código não inclui documentação explícita, como comentários ou javadocs, para descrever seu propósito ou como usá-lo. É uma boa prática adicionar documentação para tornar o código mais legível e compreensível.

2.AS VARIÁVEIS E CONSTANTES POSSUEM BOA NOMENCLATURA?
As variáveis e constantes têm nomes razoáveis, como conn, result, nome, e sql. No entanto, a nomenclatura de classes e métodos geralmente segue a convenção CamelCase, começando com uma letra maiúscula. Recomenda-se renomear a classe CaixaBranca para seguir essa convenção.

3.EXISTEM LEGIBILIDADE E ORGANIZAÇÃO NO CÓDIGO?
O código está bem estruturado e organizado em métodos. No entanto, é uma boa prática adicionar espaçamentos adequados e indentação para melhorar a legibilidade. Além disso, adicionar comentários explicativos pode ajudar a entender o que cada parte do código está fazendo.

4.TODOS OS NULLPOINTERS FORAM TRATADOS?
O código não trata explicitamente as exceções, como NullPointerException ou SQLException, que podem ocorrer em várias partes do código. É importante adicionar tratamento de exceção adequado para lidar com esses casos.

5.A ARQUITETURA UTILIZADA FOI DEVIDAMENTE RESPEITADA?
O código parece seguir uma estrutura básica para a conexão com um banco de dados MySQL e a verificação de um usuário. No entanto, a forma como a consulta SQL é montada concatenando strings não é recomendada devido a problemas de segurança (SQL Injection). Em vez disso, você deve usar Prepared Statements.

6.AS CONEXÕES UTILIZADAS FORAM FECHADAS?
O código não fecha as conexões após o uso. É importante fechar todas as conexões, instruções e resultados após o uso para evitar vazamentos de recursos. Recomenda-se adicionar blocos finally para garantir o fechamento correto das conexões.

