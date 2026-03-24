# Modelo-Conceitual-E-commerce-Entidade-de-Relacionamento-Estendida-
"Esquema conceitual para sistema de oficina mecânica, com controle de ordens de serviço, clientes, veículos, equipes de mecânicos, serviços e peças. Projeto desenvolvido para organizar processos de manutenção e revisões, garantindo rastreabilidade e integridade dos dados."
📌 Projeto Oficina Mecânica – Esquema Conceitual 

🎯 Objetivo 

Este projeto tem como finalidade implementar um esquema conceitual para controle e gerenciamento de ordens de serviço em uma oficina mecânica. O trabalho foi desenvolvido como parte da formação SQL Database Specialist (DIO), utilizando MySQL Workbench para modelagem e geração do banco de dados. 

📝 Narrativa 

Clientes levam veículos à oficina mecânica para consertos ou revisões periódicas. 

Cada veículo gera uma Ordem de Serviço (OS), que é atribuída a uma equipe de mecânicos. 

A equipe avalia o veículo, identifica os serviços necessários e registra na OS, incluindo data de emissão e previsão de conclusão. 

O valor da OS é composto pela soma dos serviços (consultados em tabela de referência de mão de obra) e das peças utilizadas. 

Os mecânicos possuem código, nome, endereço e especialidade. 

Cada OS possui número, data de emissão, valor, status e data de conclusão. 

🗂️ Entidades Principais 

Cliente: dados pessoais e contato. 

Veículo: placa, modelo, ano, vinculado ao cliente. 

Ordem de Serviço (OS): número, datas, valor, status, vínculo com veículo e equipe. 

Equipe: grupo de mecânicos responsáveis pela execução. 

Mecânico: código, nome, endereço, especialidade, vinculado a uma equipe. 

Serviço: descrição e valor de mão de obra. 

Peça: nome e valor unitário. 

ItensOS: tabela de ligação que detalha os serviços e peças aplicados em cada OS. 

🔗 Relacionamentos 

Cliente (1:N) Veículo 

Veículo (1:N) Ordem de Serviço 

Ordem de Serviço (N:1) Equipe 

Equipe (1:N) Mecânico 

Ordem de Serviço (1:N) ItensOS 

ItensOS (N:1) Serviço 

ItensOS (N:1) Peça 

📊 Fluxo de Negócio 

O cliente registra o veículo. 

O veículo gera uma Ordem de Serviço quando precisa de manutenção ou revisão. 

A OS é atribuída a uma Equipe, composta por vários Mecânicos. 

A OS detalha os Serviços e Peças através da tabela ItensOS. 

O valor final da OS é calculado pela soma dos serviços e peças. 

Observação: em oficinas pequenas, muitas vezes não existe OS formal. No entanto, neste modelo conceitual, a OS é obrigatória para garantir rastreabilidade, autorização do cliente e controle financeiro. 

🚀 Impacto na Oficina Mecânica 

🔧 Dores Reais Resolvidas 

Desorganização de ordens de serviço → elimina papéis soltos e informações perdidas. 

Falta de controle sobre peças e serviços → cada item é registrado, evitando prejuízos. 

Cálculo impreciso de valores → preços padronizados de mão de obra e peças. 

Atrasos e falta de previsibilidade → datas de emissão e conclusão registradas. 

Gestão de equipe ineficiente → atribuição clara de equipes e mecânicos. 

Histórico inexistente → consultas rápidas sobre serviços anteriores de cada veículo. 

⏱️ Tempo Economizado 

Emissão rápida de OS sem burocracia. 

Consulta imediata de preços e serviços. 

Histórico centralizado evita retrabalho. 

Distribuição de tarefas otimizada entre mecânicos. 

👉 Estimativa: redução de 20–30% do tempo administrativo. 

💰 Lucros Gerados 

Cobrança precisa evita perda de receita. 

Controle de estoque reduz desperdício de peças. 

Transparência aumenta confiança e fidelização de clientes. 

Equipes mais produtivas → menos horas ociosas. 

👉 Resultado: margens de lucro podem crescer em 10–15%. 

📈 Otimizações Estratégicas 

Organização centralizada em um único sistema. 

Transparência para clientes e gestores. 

Escalabilidade: oficina pode crescer sem perder controle. 

Relatórios estratégicos: serviços mais frequentes, peças mais usadas, desempenho das equipes. 

⚙️ Tecnologias Utilizadas 

MySQL Workbench (modelagem EER e Forward Engineer). 

MySQL Server (execução do script SQL). 

GitHub (documentação e versionamento). 

📂 Estrutura do Repositório 

script_oficina.sql → Script SQL gerado pelo Forward Engineer. 

diagrama_oficina.png → Diagrama EER exportado do Workbench. 

README.md → Documentação do projeto (este arquivo). 
