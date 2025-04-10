# Overview
Essa é uma aplicação projeto da Disciplina Integração Contínua, DevOps e Computação em Nuvem ministrada pelo Prof. Renan Oliveira.

O repositório está disponível em [https://github.com/pauloweberinfnet/infnet-guia](https://github.com/pauloweberinfnet/infnet-guia) .

A conteinerização em Docker é descrita no Dockerfile deste repositório e o container pode ser executado via `docker compose`.


## Construção da Imagem para Docker
A imagem foi construída através do comando 
```
docker build -t pauloerweber/pauloweberinfnet-infnet-guia:latest .
```

Após isso a imagem enviada para o DockerHub
```
docker push -t pauloerweber/pauloweberinfnet-infnet-guia:latest .
```

E o repositório da imagem está disponível **[aqui](https://hub.docker.com/repository/docker/pauloerweber/pauloweberinfnet-infnet-guia/general)**.

## Cluster Kubernetes
Para subir o cluster da aplicação, o comando abaixo deve ser  executado (considerando que o diretório atual é a raiz do projeto) para cada arquivo presente no diretório k8s:
```
kubectl apply -f k8s/[SERVICE OU DEPLOYMENT].yaml
```

Dentro do diretório `k8s/monitoring` estão os serviços de monitoramento que devem ser executados da mesma maneira, apenas alterando o caminho dos arquivos `yaml`.

## Testes
Os testes sao realizados pelo job K6 disponível na pasta k8s/tests.