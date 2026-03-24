#  Projeto Oficina Mecânica – Esquema Conceitual

#  Objetivo
Implementar um esquema conceitual para controle e gerenciamento de ordens de serviço em uma oficina mecânica, garantindo rastreabilidade, organização e integridade dos dados.  
Este projeto foi desenvolvido como parte da formação **SQL Database Specialist (DIO)**, utilizando MySQL Workbench para modelagem e geração do banco de dados.

# Narrativa
- Clientes levam veículos à oficina mecânica para consertos ou revisões periódicas.  
- Cada veículo é designado a uma Equipe de Mecânicos, responsável por avaliar e executar os serviços.  
- A equipe identifica os serviços necessários e gera uma Ordem de Serviço (OS), com data de emissão, previsão de entrega, status e valor total.  
- O valor da OS é composto pela soma dos serviços (consultados em tabela de referência de mão de obra) e das peças utilizadas.  
- O cliente autoriza a execução dos serviços.  
- Os mecânicos possuem código, nome, endereço e especialidade.  

# Entidades Principais
- **Cliente** → dados pessoais e contato.
- 
- **Veículo** → placa, modelo, ano, vinculado ao cliente.
-   
- **Equipe** → grupo de mecânicos responsáveis pelo veículo.
- 
- **Mecânico** → código, nome, endereço, especialidade, vinculado a uma equipe.
-  
- **Ordem de Serviço (OS)** → número, datas, valor, status, vínculo com veículo e equipe.
- 
- **Serviço** → descrição, valor de mão de obra, tempo estimado e categoria.
- 
- **Peça** → nome, valor unitário e quantidade.  

#  Relacionamentos
- Cliente (1:N) Veículo  
- Veículo (1:1) Equipe  
- Equipe (1:N) Mecânico  
- Equipe (1:N) Ordem de Serviço  
- Ordem de Serviço (N:M) Serviço  
- Serviço (1:N) Peça  

#  Fluxo de Negócio
1. O Cliente registra o Veículo.  
2. O Veículo é atribuído a uma Equipe responsável.  
3. A Equipe é composta por vários Mecânicos.  
4. A Equipe gera Ordens de Serviço para os veículos que atende.  
5. Cada Ordem de Serviço detalha os Serviços realizados.  
6. Cada Serviço pode utilizar várias Peças.  
7. O valor final da OS é calculado pela soma dos serviços e peças.  

# **Impacto na Oficina Mecânica**

#  **Dores Reais Resolvidas**
- Perda de informações críticas → substituição de registros em papel por sistema digital, garantindo rastreabilidade completa.  
- **Falta de controle financeiro** → cálculo automático e padronizado de mão de obra e peças, evitando erros e prejuízos.  
- **Gestão ineficiente de equipes** → atribuição clara de veículos e OS para cada equipe, otimizando carga de trabalho.  
- **Desperdício de peças e estoque desorganizado** → registro detalhado de peças utilizadas em cada OS, reduzindo custos e perdas.  
- **Ausência de histórico confiável** → consultas rápidas sobre serviços anteriores de cada veículo, fortalecendo relacionamento com clientes.  
- **Baixa transparência para o cliente** → OS formalizada com valores e prazos, aumentando confiança e fidelização.  

##  Tempo Economizado
- Emissão rápida de OS sem burocracia.  
- Consulta imediata de preços e serviços.  
- Histórico centralizado evita retrabalho.  
- Distribuição otimizada de tarefas entre mecânicos.  
- Estimativa: **redução de 20–30% do tempo** administrativo.  

##  Lucros Gerados
- Cobrança precisa evita perda de receita.  
- Controle de estoque reduz desperdício de peças.  
- Transparência aumenta confiança e fidelização de clientes.  
- Equipes mais produtivas → menos horas ociosas.  
- Margens de lucro podem crescer em **10–15%**.  

#  Diferenciais Competitivos
- **Escalabilidade**: modelo pronto para expansão da oficina sem perda de controle.  
- **Visão estratégica**: relatórios sobre serviços mais frequentes, peças mais usadas e desempenho das equipes.  
- **Profissionalização**: sistema formaliza processos, elevando a credibilidade da oficina.  
- **Integração**: dados centralizados permitem análises financeiras e operacionais em tempo real.  

#  Tecnologias Utilizadas
- **MySQL Workbench** → modelagem EER e Forward Engineer.  
- **MySQL Server** → execução do script SQL.  
- **GitHub** → documentação e versionamento.  

#  Estrutura do Repositório
- `script_oficina.sql` → Script SQL gerado pelo Forward Engineer.
-  
- `diagrama_oficina.png` → Diagrama EER exportado do Workbench.
-  
- `README.md` → Documentação do projeto (este arquivo).
-   
