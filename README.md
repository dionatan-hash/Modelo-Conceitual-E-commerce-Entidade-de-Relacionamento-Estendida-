#  Projeto Oficina Mecânica – Esquema Conceitual

#  Objetivo
Implementar um esquema conceitual para controle e gerenciamento de ordens de serviço em uma oficina mecânica, garantindo rastreabilidade, organização e integridade dos dados.  
Este projeto foi desenvolvido como parte da formação **SQL Database Specialist (DIO)**, utilizando MySQL Workbench para modelagem e geração do banco de dados.

> Este projeto foi desenvolvido simulando a entrega de um engenheiro de dados júnior para uma equipe sênior, levando em consideração metas e prazos reais de uma empresa. Foi elaborado com atenção aos detalhes e mentalidade de aplicação prática em um cenário corporativo .


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
- > Observação: O relacionamento Veículo–Equipe foi modelado como 1:1 para atender à narrativa do projeto, representando a ideia de que uma equipe trabalha em um veículo por vez. Em cenários reais, esse relacionamento poderia ser expandido para N:1, permitindo que uma equipe atenda vários veículos ao longo do tempo.

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

# **Impacto na Oficina Mecânica** **E**

#  **Dores Reais Resolvidas**
- **Perda de informações críticas → substituição de registros em papel por sistema digital, garantindo rastreabilidade completa.**  
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

- `diagrama_oficina.png` → Diagrama EER exportado do Workbench.
- 
-  <img width="690" height="588" alt="Captura de tela 2026-03-23 222722" src="https://github.com/user-attachments/assets/1ace29f2-aae7-4ea8-9a43-20eeaccfddb0" />

<img width="569" height="520" alt="Captura de tela 2026-03-23 212011" src="https://github.com/user-attachments/assets/2f909e2b-5615-444e-961f-c1c08ad5e138" />

- `README.md` → Documentação do projeto (este arquivo).
-   
