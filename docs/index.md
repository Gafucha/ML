# Template de Entrega


???+ info inline end "Edição"

    2025.1


## Grupo - Integrador 11

1. Gabriel Fuzita Chaves



!!! tip "Instruções"

    Vocês devem utilizar este template como um bloco de notas para registrar o que foi feito e o que falta fazer. Vocês devem adicionar as informações necessárias.
    O template deve ser editado e atualizado a cada entrega, registrando assim a data de entrega e o que foi feito até o momento via Git.

## Entregas

- [ ] Exercício 1 - Árvore de Decisão (29/08)
- [ ] Exercício 2 - KNN (16/09)
- [ ] Exercício 3 - K-Mean (19/09)
- [ ] Exercício 4 - Métricas de Avaliação (19/09)
- [ ] Projeto I (30/09)
- [ ] Exercício 5 - Random Forest (28/10)
- [ ] Exercício 6 - Support Vector Machine (07/11)
- [ ] Exercício 7 - Page Rank (18/11)
- [ ] Exercício 8 - PySpark (28/11)
- [ ] Projeto II (05/12)

## Diagramas

Use o [Mermaid](https://mermaid.js.org/intro/){:target='_blank'} para criar os diagramas de documentação.

[Mermaid Live Editor](https://mermaid.live/){:target='_blank'}


``` mermaid
flowchart TD
    Deployment:::orange -->|defines| ReplicaSet
    ReplicaSet -->|manages| pod((Pod))
    pod:::red -->|runs| Container
    Deployment -->|scales| pod
    Deployment -->|updates| pod

    Service:::orange -->|exposes| pod

    subgraph  
        ConfigMap:::orange
        Secret:::orange
    end

    ConfigMap --> Deployment
    Secret --> Deployment
    classDef red fill:#f55
    classDef orange fill:#ffa500
```



## Códigos

=== "De um arquivo remoto"

    ``` { .yaml .copy .select linenums='1' title="main.yaml" }
    --8<-- "https://raw.githubusercontent.com/hsandmann/documentation.template/refs/heads/main/.github/workflows/main.yaml"
    ```

=== "Anotações no código"

    ``` { .yaml title="compose.yaml" }
    name: app

        db:
            image: postgres:17
            environment:
                POSTGRES_DB: ${POSTGRES_DB:-projeto} # (1)!
                POSTGRES_USER: ${POSTGRES_USER:-projeto}
                POSTGRES_PASSWORD: ${POSTGRES_PASSWORD:-projeto}
            ports:
                - 5432:5432 #(2)!
    ```

    1.  Caso a variável de ambiente `POSTGRES_DB` não exista ou seja nula - não seja definida no arquivo `.env` - o valor padrão será `projeto`. Vide [documentação](https://docs.docker.com/reference/compose-file/interpolation/){target='_blank'}.

    2. Aqui é feito um túnel da porta 5432 do container do banco de dados para a porta 5432 do host (no caso localhost). Em um ambiente de produção, essa porta não deve ser exposta, pois ninguém de fora do compose deveria acessar o banco de dados diretamente.


## Exemplo de vídeo

Lorem ipsum dolor sit amet

<iframe width="100%" height="470" src="https://www.youtube.com/embed/3574AYQml8w" allowfullscreen></iframe>


## Referências

[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/){:target='_blank'}