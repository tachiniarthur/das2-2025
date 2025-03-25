# Design e Arquitetura de Software 2
SEU NOME COMPLETO DE PREFERÊNCIA, LEGÍVEL!!!

## Aula 24/02 - Well-Architected Framework  
- **Seis pilares**:
  - **Excelência Operacional**: Automação e monitoramento contínuo.  
  - **Segurança**: Controle de acessos e proteção dos dados.  
  - **Confiabilidade**: Resiliência e recuperação de falhas.  
  - **Eficiência em Performance**: Uso otimizado dos recursos.  
  - **Otimização de Custos**: Evitar desperdícios sem comprometer a qualidade.  
  - **Sustentabilidade**: Uso eficiente e consciente da infraestrutura.  

## Aula 27/02 - Trade-Offs e Infraestrutura como Código  
- **Trade-offs**: Sempre equilibrar custo, desempenho e disponibilidade.  
- **Escalabilidade vs Elasticidade**: Crescimento planejado vs ajuste dinâmico.  
- **Infraestrutura como Código (IaC)**: Automação total da infraestrutura.  
- **Recursos descartáveis**: Criar e destruir servidores sem preocupação.  
- **Baixo acoplamento**: Evitar dependências entre serviços.  
- **Design de serviços, não servidores** (focar em **serverless**).  
- **Escolha do banco de dados**: Relacional x NoSQL, dependendo da aplicação.  

## Aula 06/03 - Alta Disponibilidade e Otimização  
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

## Aula 13/03 - IAM (Identity and Access Management)  
- **IAM**: Gestão de usuários e permissões na AWS.  
- **Privilégio mínimo**: Evitar acessos desnecessários.  
- **Autenticação vs Autorização**.  
- **Formas de acesso**:  
  - Console (gráfico).  
  - Programático (CLI, SDK, chaves de acesso).  

## Aula 17/03 - Políticas de Acesso e S3  
- **Política de Identidade**: Aplicada a usuários, grupos e funções.  
- **Política de Recurso**: Aplicada diretamente a serviços (ex: S3).  
- **Amazon S3**:  
  - Armazenamento escalável.  
  - Controle de acessos e permissões.  
  - Versionamento, criptografia e gerenciamento de ciclo de vida.  

## Aula 24/03 - S3 - Gerenciamento, Versionamento e CORS  
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


