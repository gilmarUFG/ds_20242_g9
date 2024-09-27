

## **História de Usuário**

### **ID:**  
HU-002

### **Título:**  
Login com autenticação de dois fatores (2FA)

### **Descrição:**  
Como **usuário cadastrado**, eu quero **poder realizar login com autenticação de dois fatores (2FA)** para que **minha conta esteja mais protegida contra acessos não autorizados**.

### **Critérios de Aceitação:**

#### Cenário 1: Login com sucesso usando 2FA
- **Dado** que o usuário está na página de login e tem a autenticação de dois fatores ativada,
- **Quando** o usuário insere corretamente seu e-mail e senha,
- **E** é direcionado para a página de verificação de código de autenticação,
- **E** insere o código de autenticação enviado para seu dispositivo,
- **Então** o usuário deve ser autenticado com sucesso e direcionado para a página inicial.

#### Cenário 2: Falha no login por código 2FA inválido
- **Dado** que o usuário está na página de verificação de código de autenticação,
- **Quando** insere um código de autenticação incorreto,
- **Então** uma mensagem de erro deve ser exibida, informando que o código está incorreto,
- **E** o usuário deve poder tentar inserir o código novamente.

#### Cenário 3: Falha no login por expiração do código 2FA
- **Dado** que o usuário está na página de verificação de código de autenticação,
- **Quando** o código de autenticação expira (após 5 minutos),
- **Então** uma mensagem de erro deve ser exibida informando que o código expirou,
- **E** o usuário deve ter a opção de solicitar o envio de um novo código.

### **Prioridade:**  
Alta

### **Estimativa de Esforço:**  
8 Story Points

### **Dependências:**  
- Integração com o sistema de geração e envio de códigos de autenticação (História HU-006).
- Desenvolvimento da interface de verificação de código (História HU-007).

### **Notas/Comentários Adicionais:**
- O código de autenticação deve ser enviado via SMS ou aplicativo autenticador.
- Consultar a equipe de segurança sobre a validade e segurança do código de verificação.
