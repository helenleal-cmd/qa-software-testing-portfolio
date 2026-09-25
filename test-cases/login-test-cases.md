# Casos de Teste - Login

## Informações gerais

| Item | Descrição |
| --- | --- |
| Aplicação | SauceDemo |
| Funcionalidade | Login |
| Tipo de teste | Teste funcional manual |
| Ambiente | Web |
| Status da execução | Em andamento |

## TC-001 - Login com credenciais válidas

**Objetivo:** Verificar se um usuário válido consegue acessar o sistema utilizando credenciais corretas.

**Pré-condição:** Usuário deve estar na página de login do SauceDemo.

**Dados de teste:**

| Campo | Valor |
| --- | --- |
| Username | `standard_user` |
| Password | `secret_sauce` |

**Passos:**

1. Acessar a página de login.
2. Informar o username `standard_user`.
3. Informar a senha `secret_sauce`.
4. Clicar no botão **Login**.

| Resultado esperado | Resultado obtido | Status |
| --- | --- | --- |
| O sistema deve autenticar o usuário e direcioná-lo para a página de produtos. | Login realizado com sucesso e página de produtos exibida. | PASS |

## TC-002 - Login com senha inválida

**Objetivo:** Verificar se o sistema impede o acesso quando uma senha inválida é informada.

**Pré-condição:** Usuário deve estar na página de login do SauceDemo.

**Dados de teste:**

| Campo | Valor |
| --- | --- |
| Username | `standard_user` |
| Password | Senha inválida |

**Passos:**

1. Acessar a página de login.
2. Informar o username `standard_user`.
3. Informar uma senha inválida.
4. Clicar no botão **Login**.

| Resultado esperado | Resultado obtido | Status |
| --- | --- | --- |
| O sistema deve impedir o acesso e informar que as credenciais são inválidas. | Acesso bloqueado. O sistema apresentou: `Epic sadface: Username and password do not match any user in this service.` | PASS |

## TC-003 - Login com usuário inexistente

**Objetivo:** Verificar se o sistema impede o acesso quando são informadas credenciais associadas a um usuário inexistente.

**Pré-condição:** Usuário deve estar na página de login do SauceDemo.

**Dados de teste:**

| Campo | Valor |
| --- | --- |
| Username | `usuario_teste` |
| Password | `secret_sauce` |

**Passos:**

1. Acessar a página de login.
2. Informar o username inexistente `usuario_teste`.
3. Informar a senha `secret_sauce`.
4. Clicar no botão **Login**.

| Resultado esperado | Resultado obtido | Status |
| --- | --- | --- |
| O sistema deve impedir o acesso e apresentar uma mensagem de erro. | Acesso bloqueado. O sistema apresentou: `Epic sadface: Username and password do not match any user in this service.` | PASS |

## TC-004 - Login com usuário bloqueado

**Objetivo:** Verificar o comportamento do sistema ao tentar autenticar um usuário bloqueado.

**Pré-condição:** Usuário deve estar na página de login do SauceDemo.

**Dados de teste:**

| Campo | Valor |
| --- | --- |
| Username | `locked_out_user` |
| Password | `secret_sauce` |

**Passos:**

1. Acessar a página de login.
2. Informar o username `locked_out_user`.
3. Informar a senha `secret_sauce`.
4. Clicar no botão **Login**.

| Resultado esperado | Resultado obtido | Status |
| --- | --- | --- |
| O sistema deve impedir o acesso e informar que o usuário está bloqueado. | Acesso impedido. O sistema apresentou: `Epic sadface: Sorry, this user has been locked out.` | PASS |

## Resumo da execução

| ID | Cenário | Status |
| --- | --- | --- |
| TC-001 | Login com credenciais válidas | PASS |
| TC-002 | Login com senha inválida | PASS |
| TC-003 | Login com usuário inexistente | PASS |
| TC-004 | Login com usuário bloqueado | PASS |

**Total executado:** 4 casos de teste  
**Aprovados:** 4  
**Falharam:** 0  
**Taxa de aprovação:** 100%
