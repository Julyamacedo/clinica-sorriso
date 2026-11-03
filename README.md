1. Paciente
id_paciente — SERIAL PRIMARY KEY
nome — VARCHAR(100)
cpf — VARCHAR(11)

2. Dentista
id_dentista — SERIAL PRIMARY KEY
nome — VARCHAR(100)
cro — VARCHAR(20)
telefone — VARCHAR(11)

3. Consulta
id_consulta — SERIAL PRIMARY KEY
data_consulta — DATE
horario — TIMESTAMP
duracao — INTEGER
status — ENUM('Agendada', 'Cancelada', 'Realizada', 'Remarcada')
procedimento — TEXT
forma_pagamento — ENUM('PIX', 'Dinheiro', 'Débito', 'Crédito')
valor — NUMERIC(10,2)
tipo_paciente — ENUM('Normal', 'VIP')
id_paciente — INTEGER FOREIGN KEY
id_dentista — INTEGER FOREIGN KEY

Relacionamentos
Paciente — Consulta (1:N): um paciente pode realizar várias consultas, mas cada consulta pertence a um único paciente.
Dentista — Consulta (1:N): um dentista pode atender várias consultas, mas cada consulta está associada a um único dentista.

