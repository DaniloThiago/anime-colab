# Anime-Colab
### Nesse dataset os mostra atores que dublam personagens dos nossos queridos animes, dentre eles temos os animes [Blue Lock](https://www.crunchyroll.com/pt-br/series/G4PH0WEKE/bluelock), [My Dress-Up Darling](https://www.crunchyroll.com/pt-br/series/GQWH0M9N8/my-dress-up-darling), [SPY x FAMILY](https://www.crunchyroll.com/pt-br/series/G4PH0WXVJ/spy-x-family), [Overlord IV](https://www.crunchyroll.com/pt-br/series/G69PZ5PDY/overlord), [Dr. Stone: Ryuusui](https://www.crunchyroll.com/pt-br/series/GYEXQKJG6/dr-stone), entre outros grandes sucessos.

## Links:
  [Sigma](https://danilothiago.github.io/anime-actor-voice/) e [Streamlit](https://animes.streamlit.app/)

## Nesse dataset foram separados para a utilização da seguinte forma
- **Os nós serão**: Os atores que dublam os personagens
- **As aretas serão**: Os animes em que os atores trabalharam em comum

### Ou seja, se um ator está conectado a outro, é por que ambos trabalharam na mesma obra

#### OBS.: Foi necessário filtrar os nós e gerar um subgrafo, pois se fosse realizar a conexão entre todos os atores dentre todos os animes, o Pyvis (ferramente utilizada no estudo dos grafos) ficou muito lento para renderizar o conteúdo, por isso preferi realizar a filtragem pegando somente os animes maiores ou igual a 2022.

## Nesse colab encontraremos os seguintes resultados:
- **Matriz de adjacência**: Onde visualizaremos de forma matricial a relação entre os atores.
- **Diâmetro e periferia da rede**: Por existirem grafos não conectados foi gerado os subgrupos da rede e mostrados os seus respctivos valores.
- **Esparsidade/Densidade da Rede**:
  - **Esparsidade**: indica a proporção de conexões existentes em relação ao número total possível de conexões.
  - **Densidade**: é uma medida da quantidade de conexões presentes em relação ao número total possível de conexões.
- **Assortatividade**:
  - Um coeficiente de assortatividade positivo indica que os nós da rede têm uma tendência a se conectar com nós que possuem características semelhantes.
  - Um coeficiente de assortatividade negativo indica uma tendência oposta, ou seja, os nós da rede têm uma tendência a se conectar com nós que possuem características diferentes.
  - No meu estudo obtive uma assortatividade geral de 0.11254642198066878, esse valor positivo sugere que existe uma leve tendência dos atores da rede a se conectarem com outros atores que possuem características semelhantes.
- **Coeficiente de clustering local e global**:
  - **Local**:
    Para o teste de clustering local foi escolhido dois ator/atriz: [*Ayumu Murase*](https://www.animenewsnetwork.com/encyclopedia/people.php?id=113308): com clustering de 0.24761904761904763 e [*Mayu Iizuka*](https://www.animenewsnetwork.com/encyclopedia/people.php?id=127911): com clustering de  1.0;
    Os resultados sugerem que a [*Mayu Iizuka*](https://www.animenewsnetwork.com/encyclopedia/people.php?id=127911) está em um grupo muito coeso ou agrupamento denso de nós em sua vizinhança. Já a [*Ayumu Murase*](https://www.animenewsnetwork.com/encyclopedia/people.php?id=113308), por ter um valor mais baixo, indica que nem todos os seus vizinhos estão conectados entre si.
  - **Global**: Tive um resultado de 0.8305510170307192, esse valor sugere que o grafo como um todo possui uma alta tendência de formação de agrupamentos ou "clusters".
- **Componentes conectados fortemente e fracamente**: Por ser preciso ter um grafo dirigido para gerar essa métrica e meu grafo ser não dirigido, utilizei a abordagem do K-core decomposition para mostrar pelas cores os componentes fortemente e fracamente conectados.
  -  **Fortemente**: É um conjunto de nós em que cada nó pode ser alcançado a partir de qualquer outro nó desse conjunto.
  -  **Fracamente**: É um conjunto de nós em que, se você ignorar a direção das arestas, pode ser encontrado um caminho não direcionado entre qualquer par de nós.
- **Centralities**:
  - **Eigenvector**: É uma medida que atribui uma pontuação de centralidade a cada nó em uma rede com base em sua importância e na importância dos nós aos quais está diretamente conectado. Nós com uma Eigenvector Centrality alta são considerados mais centrais e têm uma maior influência na rede. Essa medida leva em consideração a importância dos nós vizinhos, portanto, um nó conectado a outros nós importantes terá uma Eigenvector Centrality mais alta.
  - **Degree**: É uma medida simples que calcula o número de conexões diretas de um nó em uma rede. Ela representa o número de arestas incidentes em um nó. Nós com um alto grau de conexões (alto número de arestas) tendem a ter uma Degree Centrality alta, indicando que são importantes ou centrais na rede. A Degree Centrality é útil para identificar nós populares ou com um grande número de conexões diretas.
  - **Closeness**: É uma medida que quantifica a proximidade de um nó para todos os outros nós na rede. Ela é baseada na distância média entre o nó em questão e todos os outros nós da rede. Nós com uma Closeness Centrality alta estão mais próximos de outros nós e, portanto, têm maior acesso e influência na rede. Essa medida é útil para identificar nós que podem disseminar informações de maneira rápida e eficiente na rede.
  - **Betweenness**: É é uma medida que quantifica a importância de um nó como ponte ou intermediário entre outros pares de nós em uma rede. Ela calcula a proporção de caminhos mais curtos entre todos os pares de nós que passam pelo nó em questão. Nós com uma Betweenness Centrality alta são cruciais para a comunicação e fluxo de informações na rede, pois atuam como intermediários na comunicação entre outros nós. Essa medida é útil para identificar nós que desempenham um papel central na comunicação e na transferência de informações na rede.
