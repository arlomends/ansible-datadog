# Automação de Monitoramento com Datadog Agent e Ansible

Este projeto automatiza o deploy do Datadog Agent (v7) utilizando Ansible e Docker. O foco deste laboratório e demonstrar a capacidade de integrar ferramentas de monitoramento SaaS (Software as a Service) em uma infraestrutura conteinerizada.

## Componentes do Projeto

* Ansible: Utilizado para a orquestração e configuração do ambiente.
* Docker: Engine para execução do agente de monitoramento de forma isolada.
* Datadog Agent: Coletor de métricas de sistema, logs e performance de containers.

## Implementação Técnica

A automacao realiza as seguintes configurações:
1. Provisionamento do container oficial do Datadog.
2. Mapeamento de volumes criticos (/proc, /sys/fs/cgroup) para monitoramento de hardware host.
3. Integração com o Docker Socket para coleta automática de métricas de outros containers.
4. Configuração de variáveis de ambiente para autenticação no site US5 do Datadog.

## Como Executar

1. Certifique-se de ter o Ansible instalado.
2. No diretório do projeto, execute:
   ansible-playbook -i ansible/inventory.ini ansible/playbook.yml --ask-become-pass

## Resultados Esperados

Após a execução bem-sucedida, o host torna-se visível no painel de Infrastructure List do Datadog, fornecendo métricas em tempo real de CPU, Memoria, Disco e integridade de containers.
