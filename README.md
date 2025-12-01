# Manowar DevOps Project

Este projeto demonstra um fluxo completo de CI/CD com GitOps para aplicações containerizadas em Kubernetes.

- Aplicação e pipeline de build/testes: https://github.com/vi-tineo/ManowarImage-CI.git  
- Repositório GitOps monitorado pelo Argo CD: https://github.com/vi-tineo/ManowarK8sGitOps-CI.git

## Fluxo
1. CI compila o código-fonte, executa testes unitários e gera a imagem Docker
2. A imagem é publicada no Docker Hub com tag baseada no commit
3. O workflow atualiza o repositório GitOps com a nova versão
4. O Argo CD detecta a mudança e aplica no cluster bare metal

## Tecnologias
- GitHub Actions
- Docker & DockerHub
- Kubernetes
- Argo CD
- GitOps
- Go

Fluxo:
[App Repo] → [CI Pipeline] → [Docker Hub]
                   ↓
          [GitOps Repo] → [Argo CD] → [Cluster]

Este projeto integra práticas modernas de DevOps e GitOps, servindo como estudo e vitrine de automação de deploys em Kubernetes.
Em um cenário real, incluiríamos um processo CI/CD intermediário para provisionamento de infraestrutura como código (IaC) com Terraform, utilizando os providers AWS e Helm. Esse pipeline seria responsável por criar e gerenciar um cluster EKS com recursos avançados como HPA e Karpenter para otimização de custos e escalabilidade, além da integração contínua com o Argo CD para entrega automatizada das aplicações.
