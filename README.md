**Clinica sorriso** 

### 1\. Paciente

* id\_paciente — SERIAL PRIMARY KEY  
* nome — VARCHAR(100)  
* cpf — VARCHAR(11)

### 2\. Dentista

* id\_dentista — SERIAL PRIMARY KEY  
* nome — VARCHAR(100)  
* cro — VARCHAR(20)  
* telefone — VARCHAR(11)

### 3\. Consulta

* id\_consulta — SERIAL PRIMARY KEY  
* data\_consulta — DATE  
* horario — TIMESTAMP  
* duracao — INTEGER  
* status — ENUM('Agendada', 'Cancelada', 'Realizada', 'Remarcada')  
* procedimento — TEXT  
* forma\_pagamento — ENUM('PIX', 'Dinheiro', 'Débito', 'Crédito')  
* valor — NUMERIC(10,2)  
* tipo\_paciente — ENUM('Normal', 'VIP')  
* id\_paciente — INTEGER FOREIGN KEY  
* id\_dentista — INTEGER FOREIGN KEY

## Relacionamentos

* Paciente — Consulta (1:N): um paciente pode realizar várias consultas, mas cada consulta pertence a um único paciente.  
* Dentista — Consulta (1:N): um dentista pode atender várias consultas, mas cada consulta está associada a um único dentista.


<img width="1225" height="708" alt="image" src="https://github.com/user-attachments/assets/de06ac08-0fa3-4b04-a66e-1c832af77c03" />


