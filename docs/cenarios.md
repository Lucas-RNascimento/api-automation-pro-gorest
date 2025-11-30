# 🧪 Cenários de Teste — API GoRest (Users)

Este documento descreve todos os cenários de teste funcionais, negativos e edge cases para o módulo **/users** da API GoRest.

---

# 1. ✔ Cenários Positivos (CRUD)

## 1.1 Criar usuário
1. Criar usuário com dados válidos
2. Criar usuário com nome contendo espaços
3. Criar usuário com e-mail gerado dinamicamente
4. Criar usuário com status "active"
5. Criar usuário com status "inactive"

---

## 1.2 Consultar usuário
6. Consultar usuário recém-criado
7. Consultar usuário existente por ID válido
8. Validar campos obrigatórios na resposta (id, name, email, gender, status)

---

## 1.3 Atualizar usuário
9. Atualizar campo name de um usuário válido
10. Atualizar campo status (active → inactive)
11. Atualizar todos os campos (PUT completo)

---

## 1.4 Listar usuários
12. Listar usuários com sucesso
13. Validar estrutura de paginação
14. Validar se a lista retorna array de objetos
15. Validar quantidade de itens por página (default = 10)

---

## 1.5 Deletar usuário
16. Deletar usuário válido
17. Confirmar que o usuário deletado não pode mais ser consultado (GET → 404)

---

# 2. ❌ Cenários Negativos

## 2.1 Criação inválida
18. Criar usuário sem enviar body
19. Criar usuário sem campo name
20. Criar usuário sem campo email
21. Criar usuário com email inválido (ex: “teste.com”)
22. Criar usuário com gender inválido
23. Criar usuário com status inválido
24. Criar usuário com e-mail já existente (violação de unique key)

---

## 2.2 Atualização inválida
25. Atualizar usuário inexistente (ID 0, -1, 999999)
26. Atualizar usuário com campos inválidos
27. Atualizar com e-mail inválido
28. Atualizar com body vazio

---

## 2.3 Consulta inválida
29. Consultar usuário inexistente
30. Consultar usuário com ID inválido (letras, símbolos)
31. Consultar usuário com ID negativo

---

## 2.4 Delete inválido
32. Deletar usuário inexistente
33. Deletar usuário com ID inválido
34. Deletar usuário duas vezes (1ª OK, 2ª deve retornar 404)

---

# 3. 🔒 Cenários de Autenticação

35. Enviar requisição sem token (deve retornar 401)
36. Enviar token inválido (401)
37. Token com formato incorreto no header
38. Token válido mas sem permissão (se aplicável)

---

# 4. 🧱 Cenários de Contrato (JSON Schema)

39. Validar contrato do GET /users
40. Validar contrato do POST /users
41. Validar contrato do PUT /users
42. Validar contrato do DELETE /users

Cada endpoint deve ser validado quanto a:
- tipos dos campos  
- campos obrigatórios  
- estrutura JSON  
- formatos (e-mail, números etc.)  

---

# 5. 🧪 Edge Cases (casos extremos)

43. Criar usuário com nome muito longo (200+ caracteres)
44. Criar usuário com caracteres especiais
45. Consultar página extremamente alta (`?page=99999`)
46. Criar usuário com espaços no email (" email@test.com ")
47. Atualizar apenas 1 campo (PATCH behavior simulado com PUT)
48. Criar usuário com campo extra não esperado
49. Enviar header Content-Type incorreto
50. Body em formato inválido (string ao invés de JSON)

---

# 6. 🧠 Observações gerais
- Emails devem ser únicos para garantir sucesso no POST.  
- A API pode remover dados antigos → usar timestamp nos testes.  
- Operações DELETE removem permanentemente.  
- Rate limit da GoRest pode gerar 429 se abusar em loops.  

---

# ✔ Total: 50 cenários completos.
Documento pronto para implementação no Postman, Insomnia e REST Assured.
