# Design e Arquitetura de Software 2
SEU NOME COMPLETO DE PREFERÊNCIA, LEGÍVEL!!!

## AULA 27/02/2025
Fazer uma arquitetura é ter que lidar com uma coisa chama trade-off (fazer escolhas).

## 24/02

Seis pilares: Excelência Operacional, Segurança, Confiabilidade, Eficiência em Performance, Otimização de Custos e Sustentabilidade.
Boa arquitetura = sistemas mais seguros, escaláveis e eficientes.
Sempre buscar automação e monitoramento contínuo.
Segurança e confiabilidade andam juntas (evitar falhas, melhorar recuperação).
Custo e eficiência precisam ser equilibrados (evitar desperdício sem comprometer performance).

## Aula 27/02

Trade-offs: Sempre existe um equilíbrio entre custo, desempenho e disponibilidade.
Escalabilidade vs Elasticidade: Escalabilidade = crescer sob demanda, Elasticidade = ajustar dinamicamente.
Infraestrutura como Código (IaC): Automação total, evitar configurações manuais.
Recursos descartáveis: Criar e destruir instâncias sem preocupação.
Baixo acoplamento: Separar componentes para evitar dependências fortes.
Focar em serviços, não servidores (serverless quando possível).
Escolher o banco de dados correto para cada caso (relacional, NoSQL, etc.).

## Aula 06/03

Evitar ponto único de falha: Sempre ter redundância (multi-AZ, backups, etc.).
Otimização de custo: Pagar apenas pelo que realmente usamos (reservar instâncias, desligar ociosas).
Uso de cache: Reduz chamadas ao banco, melhora performance.
Infraestrutura global da AWS:
Regiões: Conjuntos de data centers em locais específicos.
Zonas de Disponibilidade (AZs): Subdivisões dentro de uma região para maior redundância.
Local Zones e Data Centers: Melhoram latência para serviços específicos.

## Aula 10/03

POPs (Edge Locations): Melhoram entrega de conteúdo (CloudFront).
Modelo de responsabilidade compartilhada: AWS protege infraestrutura, nós protegemos configuração e dados.
Autenticação vs Autorização: Quem entra e o que pode fazer.
Princípio do privilégio mínimo: Conceder apenas o necessário.
Criptografia: Sempre proteger dados em repouso e em trânsito.

## Aula 13/03

IAM = Controle de usuários e permissões na AWS.
Privilégio mínimo novamente (evitar permissões desnecessárias).
Autenticação vs Autorização (login x permissões).
Formas de acesso:
Console (gráfico).
Programático (CLI, SDK, chaves de acesso).

## Aula 17/03

Política de Identidade: Aplicada a usuários, grupos e funções.
Política de Recurso: Aplicada diretamente aos serviços (ex: S3).
S3: Armazenamento escalável, configurar permissões corretamente.
Segurança do S3: Controle de acessos, criptografia, versionamento de objetos.






