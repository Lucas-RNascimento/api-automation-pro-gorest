# 📄 Plano de Teste — API GoRest (Users)

## 1. 🎯 Objetivo
Validar o módulo **/users** da API GoRest garantindo que o comportamento dos endpoints está correto, estável e seguro.  
Os testes incluem fluxos positivos, negativos, edge cases, contrato, autenticação e regras básicas de negócio.

---

## 2. 📌 Escopo

### ✔ Incluído
- Testes funcionais (CRUD completo)
- Testes negativos
- Testes de validação de dados
- Testes de contrato (JSON Schema)
- Testes básicos de autenticação (Bearer Token)
- Paginação e filtros

### ✖ Fora do escopo
- Testes de UI
- Testes de performance avançados
- Testes de integração com banco de dados
- Testes de carga (K6 / JMeter)

---

## 3. 📍 Endpoints analisados
```
GET     /users
GET     /users/{id}
POST    /users
PUT     /users/{id}
DELETE  /users/{id}
```

---

## 4. ⚙ Estratégia de Teste

### 4.1 Funcionais (Positivos)
- Criar usuário válido  
- Consultar usuário existente  
- Atualizar usuário  
- Listar usuários  
- Deletar usuário válido  

### 4.2 Negativos
- Criar usuário sem campos obrigatórios  
- Criar usuário com e-mail inválido  
- Token ausente  
- Token inválido  
- Atualizar usuário inexistente  
- Consultar ID inválido ou inexistente  
- Deletar ID inexistente  

### 4.3 Validação de Contrato
- JSON Schema aplicado via Postman e REST Assured  
- Verificação de tipos  
- Campos obrigatórios  
- Estrutura da resposta  

### 4.4 Autenticação
- Validação do header Authorization  
- Resposta 401 para token inválido  
- Resposta 401 para token ausente  

### 4.5 Paginação e limites
- Validação de resposta padrão da página 1  
- Verificação do header “X-Pagination-Limit” (quando aplicável)  
- Página inválida (ex: -1, 0, 9999)  

---

## 5. 📊 Critérios de Aceite (Definition of Ready)
A user story está pronta para teste quando:
- API está funcional  
- Token válido está disponível  
- Documentação dos endpoints está acessível  
- Ambiente estável  

---

## 6. ✔ Critérios de Saída (Definition of Done)
- Todos os testes executados  
- Nenhum defeito crítico pendente  
- Cenários negativos validados  
- Documentação do teste atualizada  
- Resultados documentados  

---

## 7. 🧪 Dados de Teste

### 7.1 Dados válidos
```json
{
  "name": "Lucas QA Automation",
  "email": "lucas.qa{{timestamp}}@mail.com",
  "gender": "male",
  "status": "active"
}
```

### 7.2 Dados inválidos
- name vazio  
- email sem @  
- gender inválido (ex: “te
