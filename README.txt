PROJETO DE GRAFOS 2017.1
Alocação de Frequência em Redes de Telecomunicação
Pedro Victor Borges Caldas da Silva
Brunno Moreira da Silva

Especificações do computador:
------------------
System Information
------------------
      Time of this report: 6/5/2017, 09:13:23
         Operating System: Windows 10 Pro 64-bit (10.0, Build 14393) (14393.rs1_release_sec.170427-1353)
             System Model: Z97X-SLI
                Processor: Intel(R) Core(TM) i7-4790K CPU @ 4.00GHz (8 CPUs), ~4.0GHz
                   Memory: 16384MB RAM
                Card name: NVIDIA GeForce GTX 970

Foi feito usando o google chrome mais atualizado para os testes.

Instruções:
Para rodar os scrips, apenas abra o index.html em um browser.Ao abri-lo um grafo inicial será apresentado.
Para ver informações adicionais abra o console de desenvolvedor do browser(F12 no google chrome).
Há outras instancias na pasta js com o nome dataSetx.txt.Para abrir essas instâncias, clique no file picker na página inicial
e selecione um dos data sets.O script irá automaticamente criar um grafo e executar o algoritmo de t-coloring.
Ao término do algoritmo uma mensagem irá dizer o tempo de processamento.Caso o algoritmo não encontre uma coloração com as
cores e restrições disponíveis ele irá imprimir outra mensagem dizendo que não conseguiu.

Arquivos de DataSets:
Os arquivos contém na primeira linha o domínio de cores disponíveis, na segunda linha as restrições de coloração e na terceira
linha o número de vértices e arestas, respectivamente.Da quarta linha em diante são as arestas.
Link para os datasets: http://www.info.univ-angers.fr/pub/porumbel/graphs/

Observações:
1) O grafo coloca algumas cores mas essas cores estão em um array com 13 cores, então caso haja um grafo que tenha mais de 13 cores,
a cor default vai ser o cinza.
2) O tempo de execução pode variar muito dependendo do sistema utilizado.
3) Instâncias grandes podem demorar mais de 1min para conluir

/*
 * Grafo G : Grafo contendo uma lista de vértices e uma lista de arestas
 * Domínio D : Lista contendo as cores disponíveis para a coloração
 * Restrições T : Lista contendo as restrições de coloração do grafo
 */
função TColoring(Grafo G, Domínio D, Restrições T) {
    Ordena os vértices v em G em ordem decrescente de grau;
    Dá uma cor inicial ao vértice de maior grau;
    Atualiza o grau de saturação dos vizinhos do vértice de maior grau;

    Enquanto houver vértice não coloridos {
        Encontrar o vértice u com o maior grau de saturação;
        Acha a menor cor possível para o vértice u respeitando o domínio D de cores e T de restrições; (Descrito na função minColor)
        Atualiza o grau de saturação dos vizinhos do vértice u;
    }
}

/*
 * Node n : Grafo contendo uma lista de vértices e uma lista de arestas
 */
função minColor(Vértice n) {
    Acha as cores sendo usadas pelos vizinhos do vértice  n;
    Para cada cor disponível verifica se ela não está sendo usada por algum dos vizinhos
    ou se a restrição é violada;
}
