# dio-formacao-sql-databse-specialist-desafio-2

Banco de Dados – Oficina Mecânica

Este repositório documenta a modelagem de um banco de dados relacional para uma oficina mecânica, conforme o Diagrama Entidade-Relacionamento (DER) anexo.

O modelo foi projetado para controlar clientes, veículos, mecânicos, especialidades, ordens de serviço, serviços executados e peças utilizadas, garantindo rastreabilidade completa das atividades da oficina.

⸻

📌 Visão Geral da Modelagem

A modelagem contempla os seguintes aspectos principais:
	•	Cadastro de clientes e seus veículos
	•	Associação flexível entre mecânicos e veículos
	•	Controle de especialidades dos mecânicos
	•	Emissão e acompanhamento de ordens de serviço (OS)
	•	Registro de serviços executados e peças utilizadas em cada OS
	•	Uso de tabelas associativas para relacionamentos muitos-para-muitos

⸻

👤 Clientes e Veículos

Entidade Cliente

Representa o cliente da oficina.

Atributos principais:
	•	Identificador do cliente
	•	Nome do cliente

Entidade Veiculo

Representa os veículos pertencentes aos clientes.

Relacionamento:
	•	Cliente → Veículo: 1:N
	•	Um cliente pode possuir vários veículos
	•	Um veículo pertence a um único cliente

⸻

👨‍🔧 Mecânicos

Entidade Mecanico

Armazena os dados cadastrais e de endereço dos mecânicos da oficina.

Especialidades dos Mecânicos
	•	Entidade Especialidade
	•	Tabela associativa Mecanico_has_Especialidade

Relacionamento:
	•	Mecânico ↔ Especialidade: N:N
	•	Um mecânico pode possuir várias especialidades
	•	Uma especialidade pode ser atribuída a vários mecânicos

⸻

🚗 Associação Mecânico × Veículo

Tabela Mecanico_has_Veiculo

Permite associar mecânicos a veículos específicos.

Relacionamento:
	•	Mecânico ↔ Veículo: N:N

Esse relacionamento possibilita o registro de quais mecânicos atuaram ou são responsáveis por determinados veículos.

⸻

🧾 Ordens de Serviço (OS)

Entidade OS

Representa uma ordem de serviço emitida pela oficina.

Atributos relevantes:
	•	Data de emissão
	•	Status da OS
	•	Data de conclusão
	•	Valores totais de serviços, peças e valor final

Mecânicos na OS
	•	Tabela associativa OS_has_Mecanico

Relacionamento:
	•	OS ↔ Mecânico: N:N
	•	Uma OS pode envolver vários mecânicos
	•	Um mecânico pode atuar em várias OS

⸻

🛠️ Serviços

Entidade Servico

Representa os serviços oferecidos pela oficina (ex.: troca de óleo, alinhamento, revisão).

Associação com OS
	•	Tabela associativa OS_has_Servico

Relacionamento:
	•	OS ↔ Serviço: N:N
	•	Uma OS pode conter vários serviços
	•	Um serviço pode aparecer em várias OS

⸻

🔩 Peças

Entidade Peca

Representa as peças utilizadas nos serviços da oficina.

Associação com OS
	•	Tabela associativa OS_has_Peca

Relacionamento:
	•	OS ↔ Peça: N:N
	•	Uma OS pode utilizar várias peças
	•	Uma peça pode ser utilizada em diferentes OS

⸻

🧩 Tabelas Associativas

O modelo utiliza tabelas associativas para representar relacionamentos muitos-para-muitos:
	•	Mecanico_has_Veiculo
	•	Mecanico_has_Especialidade
	•	OS_has_Mecanico
	•	OS_has_Servico
	•	OS_has_Peca

Essas tabelas garantem flexibilidade e integridade relacional.

⸻

🔐 Boas Práticas de Modelagem
	•	Uso de chaves primárias artificiais (IDs)
	•	Integridade referencial por meio de chaves estrangeiras
	•	Normalização para evitar redundância
	•	Separação clara entre entidades e relacionamentos

⸻

📄 Considerações Finais

Este modelo atende bem a cenários acadêmicos e pode ser facilmente expandido para uso prático, incluindo:
	•	Controle de horas trabalhadas por mecânico
	•	Valores individuais por serviço ou peça na OS
	•	Histórico de status da OS
	•	Controle de garantia de serviços

📌 DER: consulte a imagem do diagrama para visualizar todas as entidades e relacionamentos.
