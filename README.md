# 🚀 API Automation PRO — GoRest  
Automação completa de testes de API utilizando **Postman**, **Insomnia** e **REST Assured (Java)**.  
Este projeto faz parte de um portfólio profissional para demonstrar experiência prática em QA Automation.

---

## 📌 Visão Geral
Este projeto simula um cenário real de QA Backend para validar o módulo **Users** da API pública GoRest.

A automação cobre:
- CRUD completo
- Cenários positivos, negativos e edge cases
- Testes funcionais de API
- Validação de contrato (schema)
- Autenticação via Bearer Token
- Padrão de arquitetura de automação em REST Assured
- Collections profissionais em Postman e Insomnia

---

## 🧪 Tecnologias Utilizadas
- **Postman** (coleções + testes)
- **Insomnia** (workspace equivalente)
- **Java + REST Assured**
- **Maven**
- **JUnit 5**
- **Allure Reports**
- **GitHub**

---

## 📂 Estrutura do Repositório
A estrutura segue um padrão profissional de automação:

```
postman/
 ├── collections/     → Collections da API
 └── environments/    → Environment com token e variáveis

insomnia/             → Workspace com os mesmos endpoints

rest-assured/
 └── src/
     ├── main/java/   → Configs, models, specs
     └── test/java/   → Testes organizados por funcionalidades

docs/
 ├── plano-de-teste.md
 ├── cenarios.md
 ├── arquitetura.md
 └── lessons-learned.md

README.md             → Este arquivo
```

---

## 🧩 Endpoints testados (Users — GoRest)
```
GET     /users
GET     /users/{id}
POST    /users
PUT     /users/{id}
DELETE  /users/{id}
```

---

## 🛠 Como executar os testes (REST Assured)
1. Instale as dependências:
```bash
mvn clean install
```

2. Execute todos os testes:
```bash
mvn test
```

3. Gerar relatório Allure:
```bash
allure serve allure-results
```

---

## 🗂 Documentação do Projeto
- 📄 Plano de Teste → `docs/plano-de-teste.md`  
- 🧪 Cenários → `docs/cenarios.md`  
- 🧱 Arquitetura da Automação → `docs/arquitetura.md`  
- 🧠 Lessons Learned → `docs/lessons-learned.md`

---

## 🎯 Objetivo do Projeto
Demonstrar:
- Conhecimento técnico em automação de API  
- Boas práticas de arquitetura  
- Organização de projeto  
- Capacidade de documentação técnica  
- Proficiência com ferramentas amplamente usadas no mercado  

---

## 👨‍💻 Autor
**Lucas Ramalho**  
QA Automation Engineer  
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/Lucas-RNascimento)
