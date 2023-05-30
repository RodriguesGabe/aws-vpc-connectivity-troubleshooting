# Solução de Problema de Conexão em VPC na AWS

## Descrição

Este projeto documenta a solução adotada para resolver um problema de conexão em uma Virtual Private Cloud (VPC) na Amazon Web Services (AWS). Através da revisão e alteração das configurações de rede da VPC, foi possível restabelecer a conectividade afetada. Destinado a estudantes e profissionais de tecnologia interessados em solucionar problemas de conexão em VPCs na AWS, esse projeto faz parte do Laboratório no AWS Cloud Quest, um ambiente de aprendizado prático para aprimorar as habilidades dos participantes com os serviços e recursos da AWS, que oferece cenários baseados em situações reais. 

Elaborei esta documentação com o objetivo de criar um registro detalhado do laboratório e fornecer uma solução implementada adicionando medidas preventivas, para evitar problemas futuros de conectividade na VPC.

## Contexto

Uma empresa recentemente migrou seus serviços para a nuvem AWS e está enfrentando problemas de conectividade. As instâncias EC2 não conseguem se conectar à internet, e os bancos de dados não conseguem se comunicar com as instâncias.

## Desafio

O desafio consiste em configurar corretamente as tabelas de roteamento e os grupos de segurança na nuvem AWS para resolver os problemas de conectividade. A arquitetura atual inclui um Internet Gateway, um roteador, instâncias na nuvem AWS dentro de uma VPC, com sub-redes pública e privada. O servidor da web está na sub-rede pública e o servidor de banco de dados na sub-rede privada.

## Solução

Para solucionar os problemas de conectividade, serão realizadas as seguintes ações:

1. Configurar a tabela de roteamento: Será revisada a tabela de roteamento da VPC para garantir que esteja corretamente configurada para encaminhar o tráfego entre as sub-redes e a internet. Será adicionada uma rota padrão que aponta para o Internet Gateway a fim de permitir que as instâncias EC2 se conectem à internet.

2. Anexar o Internet Gateway: Será anexado o Internet Gateway à VPC para permitir a comunicação entre a VPC e a internet.

3. Configurar grupos de segurança: Serão revisados e configurados os grupos de segurança para permitir as comunicações necessárias. Serão abertas as portas apropriadas para permitir a comunicação entre as instâncias EC2 na sub-rede pública e os bancos de dados na sub-rede privada.


## Arquitetura

<div align="center">
<img src="https://github.com/RodriguesGabe/aws-vpc-connectivity-troubleshooting/assets/105085377/da394f52-a3ac-41d5-a4b0-8a4b9651d3a9" width="700px" 
</div>
  
## Serviços Utilizados

## Passo a Passo

1. Acessar o console da AWS e navegar até a seção de gerenciamento da VPC.
2. Revisar e atualizar a tabela de roteamento da VPC, adicionando uma rota padrão para o Internet Gateway.
3. Anexar o Internet Gateway à VPC.
4. Acessar a seção de grupos de segurança e revisar o grupo de segurança associado às instâncias EC2 na sub-rede pública.
5. Adicionar regras de entrada no grupo de segurança para permitir o tráfego necessário, como HTTP/HTTPS.
6. Acessar a seção de grupos de segurança e revisar o grupo de segurança associado aos bancos de dados na sub-rede privada.
7. Adicionar regras de entrada no grupo de segurança para permitir o tráfego necessário, como a porta do banco de dados.
8. Testar a conectividade entre as instâncias EC2 e a internet, e entre os bancos de dados e as instâncias EC2.

## Resultados

Após realizar as alterações nas configurações de rede, os problemas de conectividade devem ser resolvidos. As instâncias EC2 conseguirão se conectar à internet e os bancos de dados poderão se comunicar com as instâncias corretamente.

## Conclusão

Neste projeto, foi possível solucionar com sucesso os problemas de conectividade enfrentados pela empresa após a migração para a nuvem AWS. A revisão e alteração das configurações de rede da VPC foram essenciais para restabelecer a conectividade entre as instâncias EC2 e a internet, bem como permitir a comunicação adequada entre os bancos de dados e as instâncias. Ao configurar corretamente a tabela de roteamento, anexar o Internet Gateway e ajustar os grupos de segurança, conseguimos resolver os problemas de conectividade, garantindo que os serviços na nuvem funcionem de maneira eficiente.

## Recursos Adicionais

Aqui estão alguns recursos adicionais que podem ser úteis para aprender mais sobre as configurações de rede da VPC na AWS:

- [Documentação Oficial da AWS - Virtual Private Cloud (VPC)]https://docs.aws.amazon.com/vpc/index.html 
- [Guia de Configuração da VPC na AWS] https://aws.amazon.com/pt/getting-started/hands-on/build-an-amazon-vpc/ 

## Contribuição

Encorajamos a contribuição de outras pessoas para a documentação deste projeto. Caso você queira contribuir, sinta-se à vontade para abrir um problema (issue) ou enviar um pull request no repositório do projeto no GitHub. Suas contribuições são valiosas para melhorar e expandir o conhecimento compartilhado.

## Vídeo de Demonstração

