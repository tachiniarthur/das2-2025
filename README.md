# Design e Arquitetura de Software 2
SEU NOME COMPLETO DE PREFERÊNCIA, LEGÍVEL!!!

## 🗓️ Aula 24/02 - Well-Architected Framework  
- **Seis pilares**:
  - **Excelência Operacional**: Automação e monitoramento contínuo.  
  - **Segurança**: Controle de acessos e proteção dos dados.  
  - **Confiabilidade**: Resiliência e recuperação de falhas.  
  - **Eficiência em Performance**: Uso otimizado dos recursos.  
  - **Otimização de Custos**: Evitar desperdícios sem comprometer a qualidade.  
  - **Sustentabilidade**: Uso eficiente e consciente da infraestrutura.  

## 🗓️ Aula 27/02 - Trade-Offs e Infraestrutura como Código  
- **Trade-offs**: Sempre equilibrar custo, desempenho e disponibilidade.  
- **Escalabilidade vs Elasticidade**: Crescimento planejado vs ajuste dinâmico.  
- **Infraestrutura como Código (IaC)**: Automação total da infraestrutura.  
- **Recursos descartáveis**: Criar e destruir servidores sem preocupação.  
- **Baixo acoplamento**: Evitar dependências entre serviços.  
- **Design de serviços, não servidores** (focar em **serverless**).  
- **Escolha do banco de dados**: Relacional x NoSQL, dependendo da aplicação.  

## 🗓️ Aula 06/03 - Alta Disponibilidade e Otimização  
- **Evitar ponto único de falha**: Sempre usar redundância.  
- **Otimização de custos**: Reservar instâncias, desligar recursos ociosos.  
- **Uso de cache**: Reduz chamadas ao banco e melhora a performance.  
- **Infraestrutura global da AWS**:  
  - **Regiões**: Conjuntos de data centers.  
  - **Zonas de Disponibilidade (AZs)**: Redundância dentro das regiões.  
  - **Local Zones** e **Data Centers**: Melhoram latência para aplicações específicas.  

## 🗓️ Aula 10/03 - Segurança na AWS  
- **POPs (Edge Locations)**: Aceleram entrega de conteúdo (CloudFront).  
- **Modelo de responsabilidade compartilhada**:  
  - AWS protege a infraestrutura.  
  - Usuário gerencia permissões e dados.  
- **Autenticação vs Autorização**: Definir quem acessa e o que pode fazer.  
- **Princípio do privilégio mínimo**: Conceder apenas as permissões essenciais.  
- **Criptografia**: Sempre proteger dados armazenados e em trânsito.  

## 🗓️ Aula 13/03 - IAM (Identity and Access Management)  
- **IAM**: Gestão de usuários e permissões na AWS.  
- **Privilégio mínimo**: Evitar acessos desnecessários.  
- **Autenticação vs Autorização**.  
- **Formas de acesso**:  
  - Console (gráfico).  
  - Programático (CLI, SDK, chaves de acesso).  

## 🗓️ Aula 17/03 - Políticas de Acesso e S3  
- **Política de Identidade**: Aplicada a usuários, grupos e funções.  
- **Política de Recurso**: Aplicada diretamente a serviços (ex: S3).  
- **Amazon S3**:  
  - Armazenamento escalável.  
  - Controle de acessos e permissões.  
  - Versionamento, criptografia e gerenciamento de ciclo de vida.  

## 🗓️ Aula 24/03 - S3 - Gerenciamento, Versionamento e CORS  
- **Gerenciamento de ciclo de vida**:  
  - Mover ou excluir objetos automaticamente (ex: arquivar no **Glacier**).  
- **Versionamento**:  
  - Mantém versões antigas dos arquivos.  
  - Aumenta custo, então precisa ser bem gerenciado.  
- **CORS (Cross-Origin Resource Sharing)**:  
  - Define quais origens podem acessar o S3.  
  - **Exemplo de configuração:**
    ```json
    [
      {
        "AllowedHeaders": ["*"],
        "AllowedMethods": ["GET", "PUT", "POST", "DELETE"],
        "AllowedOrigins": ["http://127.0.0.1:5500"],
        "ExposeHeaders": [
          "x-amz-server-side-encryption",
          "x-amz-request-id",
          "x-amz-id-2"
        ],
        "MaxAgeSeconds": 3000
      }
    ]
    ```
## 🗓️ Aula 03/04 - EC2, EBS e AMI

- **EC2 (Elastic Compute Cloud)**:
  - Serviço de computação da AWS (servidores virtuais).
  - Permite escalar instâncias conforme a demanda.
  - Diversos tipos de instância (otimizadas para memória, CPU, etc.).

- **EBS (Elastic Block Store)**:
  - Armazenamento em bloco para EC2.
  - Persistente, mesmo se a instância for parada.
  - Tipos diferentes: SSD, HDD, provisionado por IOPS, etc.

- **AMI (Amazon Machine Image)**:
  - Imagem usada para lançar instâncias EC2.
  - Contém o SO, configs e apps pré-instalados.
  - Pode ser personalizada e reutilizada.

---

## 🗓️ Aula 07/04 - Placement Groups e Modelos de Compra EC2

- **Placement Groups**:
  - Estratégias para distribuir instâncias:
    - **Cluster**: todas próximas fisicamente → baixa latência, alta performance.
    - **Spread**: separadas em hardware distinto → mais resiliência.
    - **Partition**: grupos lógicos dentro de AZs → ideal para grandes volumes.

- **Modelos de compra do EC2**:
  - **On-Demand**: paga conforme uso, ideal para cargas variáveis.
  - **Reserved**: contrato de 1 ou 3 anos → mais barato, ideal para uso contínuo.
  - **Savings Plans**: compromisso com uso em tempo, mais flexível que reserved.
  - **Spot Instances**: até 90% mais barato, mas podem ser interrompidas.

---

## 🗓️ Aula 10/04 - RDS e Tipos de Bancos de Dados

- **RDS (Relational Database Service)**:
  - Banco relacional gerenciado (automatiza backup, patch, escalabilidade).
  - Suporta vários motores: MySQL, PostgreSQL, Oracle, SQL Server, etc.
  - Possui Multi-AZ e Read Replicas para alta disponibilidade e performance.

- **Bancos de dados relacionais**:
  - Estruturados em tabelas, com esquema fixo (SQL).
  - Usados quando há integridade e relacionamentos complexos.
  - Ex: MySQL, PostgreSQL, Oracle.

- **Bancos de dados não relacionais (NoSQL)**:
  - Flexíveis, sem esquema fixo.
  - Alta escalabilidade horizontal, ideal para grandes volumes de dados variados.
  - Tipos: documentos, chave-valor, grafos, colunas.
  - Ex: DynamoDB (chave-valor/documento), MongoDB, Cassandra.

# Segundo Bimestre

## 🗓️ Aula 05/05 - VPC, CIDR e Subnet Pública

- **VPC (Virtual Private Cloud)**:
  - Rede virtual privada dentro da AWS.
  - Permite isolar recursos e controlar acessos.
- **CIDR (Classless Inter-Domain Routing)**:
  - Define o tamanho da VPC e suas subnets (ex.: 10.0.0.0/16).
- **Subnet Pública**:
  - Subnet com rota para a internet via Internet Gateway (IGW).
  - Permite que instâncias tenham IP público e sejam acessíveis externamente.

---

## 🗓️ Aula 12/05 - Laboratórios Canvas (Guided e Challenge Lab)

- **Guided Lab: Creating a Virtual Private Cloud**:
  - Passo a passo para criar uma VPC básica.
  - Criação de subnets, rotas e configurações de segurança.
- **Challenge (Café) Lab**:
  - Simulação de ambiente real.
  - Criar a infraestrutura de rede para o Café, configurando subnets e rotas.

---

## 🗓️ Aula 15/05 - Laboratórios Canvas (Guided e Challenge Lab)

- Reforço dos laboratórios anteriores:
  - **Guided Lab**: criação básica da VPC com subnets, IGW e rotas.
  - **Challenge Lab**: cenário prático simulando uma rede para o Café.
  - Prática essencial para consolidar conhecimento sobre redes na AWS.

---

## 🗓️ Aula 19/05 - VPC Peering, AWS VPN e Direct Connect

- **VPC Peering**:
  - Conectar VPCs diferentes para comunicação privada.
  - Importante para integrar ambientes separados.
- **AWS VPN Site-to-Site**:
  - Conexão segura entre a VPC e um data center local (on-premises).
  - Usa IPsec para criptografia.
- **AWS Direct Connect**:
  - Conexão física dedicada entre a AWS e a infraestrutura local.
  - Reduz latência e melhora performance de rede.

---

## 🗓️ Aula 26/05 - IAM Groups, Roles e Cognito

- **IAM Groups**:
  - Organizar usuários e aplicar políticas em grupo.
- **Roles (funções)**:
  - Permissões temporárias para serviços ou usuários externos.
  - **AWS STS (Security Token Service)**: fornece tokens de sessão temporária.
- **AWS Cognito**:
  - Gerencia autenticação e autorização de usuários (login federado).
  - Útil para apps web/mobile.

---

## 🗓️ Aula 29/05 - Criptografia

- **Criptografia Simétrica**:
  - Usa a mesma chave para criptografar e descriptografar.
  - Mais rápida, mas menos flexível para compartilhamento.
  - Ex.: AES.
- **Criptografia Assimétrica**:
  - Usa um par de chaves: pública e privada.
  - Mais segura para troca de dados entre partes diferentes.
  - Ex.: RSA.

## 🗓️ Aula 16/06 - Load Balancer e DNS

- **Load Balancer (Balanceador de Carga)**:
  - Distribui automaticamente o tráfego entre múltiplas instâncias.
  - Aumenta a **alta disponibilidade** e **tolerância a falhas**.
  - Tipos na AWS:
    - **ALB (Application Load Balancer)**: Camada 7 (HTTP/HTTPS), ideal para apps web.
    - **NLB (Network Load Balancer)**: Camada 4 (TCP/UDP), performance alta.
    - **CLB (Classic Load Balancer)**: legado, suporte básico a camadas 4 e 7.
  - Pode ser configurado com **health checks** para garantir que só instâncias saudáveis recebam tráfego.

- **DNS (Domain Name System)**:
  - Traduz nomes de domínio (ex: `exemplo.com`) para endereços IP.
  - Na AWS, o serviço de DNS é o **Route 53**.
  - Suporta **balanceamento de carga com DNS**, **failover**, **geolocalização**, entre outros.
  - Importante para conectar domínios aos serviços hospedados na AWS.

---

## 🗓️ Aula 23/06 - Infraestrutura como Código (IaC)

- **Infraestrutura como Código (IaC)**:
  - Permite criar e gerenciar infraestrutura com arquivos de configuração.
  - Traz **automação**, **repetibilidade**, **controle de versão** e **consistência**.
  - Evita configuração manual e reduz erro humano.

- **Ferramentas populares**:
  - **AWS CloudFormation**:
    - Ferramenta nativa da AWS.
    - Usa arquivos YAML ou JSON.
    - Permite definir toda a infraestrutura como um template.
  - **Terraform**:
    - Ferramenta open source.
    - Multicloud (AWS, Azure, GCP, etc.).
    - Usa linguagem declarativa (HCL).

- **Benefícios do IaC**:
  - Implantação rápida e padronizada.
  - Fácil escalabilidade.
  - Ideal para ambientes DevOps e CI/CD.

## 🗓️ Aula 26/06 - Como Reduzir o Acoplamento das Aplicações

- **Acoplamento** = nível de dependência entre componentes de um sistema.
  - Quanto mais acoplados, mais difícil manter, escalar e testar.

### 🔧 Estratégias para reduzir o acoplamento:

- **Dividir responsabilidades (princípio da responsabilidade única)**  
  - Cada serviço/componente deve fazer uma única coisa bem definida.

- **Arquitetura em microsserviços**  
  - Separar a aplicação em serviços menores e independentes.
  - Comunicação entre serviços via **APIs** ou **mensageria**.

- **Utilizar filas e eventos (mensageria assíncrona)**  
  - Ex: SQS, SNS, Kafka.
  - Permite que serviços se comuniquem de forma desacoplada.

- **Evitar chamadas diretas entre serviços**  
  - Usar gateways, barramentos de eventos ou middlewares.

- **Definir contratos bem claros entre os serviços (APIs)**  
  - Padronizar respostas, endpoints e formatos de dados.

- **Separação entre camadas (MVC, por exemplo)**  
  - Manter lógicas distintas separadas (ex: controller, service, repository).

- **Injeção de dependência (Dependency Injection)**  
  - Reduz a rigidez entre classes/módulos, facilitando testes e trocas.

- **Uso de banco de dados separado por serviço** (em microsserviços)  
  - Evita dependência compartilhada e conflitos de schema.

### Benefícios:
- Facilita manutenção e evolução do sistema.
- Aumenta testabilidade.
- Permite deploys independentes.
- Aumenta a resiliência e escalabilidade.
