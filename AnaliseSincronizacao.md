# Atividade Prática 01
* Execute o programa MeuDadoThreads, de modo que ele gere uma log da execução;
* Execute novamente o mesmo programa, de modo que gere uma nova log de executação sem sobrescrever a anterior;
* Compare as duas execuções e verifique se o resultado foi diferente.

  Na primeira execução, o comportamento das threads foi mais desorganizado, com o consumidor lendo valores várias vezes, como os casos de Consumidor: 14 e Consumidor: 19. Isso indica que o consumidor estava consumindo mais lentamente do que o produtor, o que resultou em repetição de leitura de certos valores enquanto o produtor avançava com novos dados. Essa desorganização sugere uma interleaving mais irregular entre as threads.
  Na segunda execução, a ordem entre produção e consumo foi mais equilibrada. O consumidor consumiu valores de forma mais linear, sem tantas repetições, como observado em Consumidor: 24 e Consumidor: 26. Contudo, ainda houve alguns casos de consumo de valores repetidos, o que é esperado em um ambiente concorrente, mas de maneira mais controlada do que na execução anterior.

# Atividade Pratica 02:
* Execute o programa MeuDadoMonitorJava.java, de maneira que gere uma log da execução;
* Realize uma comparação desta execução com as duas execuções anteriores;

  Na primeira execução, o Produtor armazena o valor 0, o Consumidor consome o valor 0, e o Produtor armazena o valor 1. A sincronização parece estar funcionando corretamente, pois o Consumidor só consome o valor após o Produtor ter armazenado o dado. A interação entre as threads ocorre de maneira coordenada e sem falhas.
  Já na segunda, o Produtor armazena o valor 0, o Consumidor consome o valor 0, e o Produtor armazena o valor 1. Embora a ordem de execução das threads seja ligeiramente diferente da Execução 1, o comportamento geral continua o mesmo. O Consumidor só consome após o Produtor ter armazenado o dado.
  Ao comparar as duas execuções, percebemos que ambas são semelhantes, com pequenas variações na ordem de execução das threads. No entanto, a sincronização entre as threads garante que o Consumidor sempre consuma o dado após o Produtor tê-lo armazenado, sem falhas ou inconsistências.


# Atividade Prática 03
* Execute o programa [MeuDadoEventJava](./MeuDadoEventJava.java), de modo que gere uma log da execução;
* Realize uma comparação dos resultados desta execução com os obtidos com as execuções da Atividade Pratica 01 e 02;

  Execução Atividade Prática 01 (com synchronized): O Produtor e o Consumidor alteram entre si quase imediatamente. A alternância entre os dois parece ser perfeita, sem grandes intervalos.
  Execução Atividade Prática 02 (com Monitores): O comportamento é similar ao anterior, mas pode ocorrer algum atraso em algumas situações, já que o controle do acesso ao dado é feito com monitores, o que pode resultar em pequenas variações entre a execução das threads.
  Execução Atividade Prática 03 (com wait/notify): O uso de wait() e notify() oferece um controle mais explícito entre o Produtor e o Consumidor, onde o Produtor espera que o Consumidor consuma antes de armazenar o próximo dado, e vice-versa. Isso pode levar a uma alternância mais clara entre o armazenamento e o consumo dos dados.
