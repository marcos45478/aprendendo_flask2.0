📌 Sistema de Cadastro e Login com Flask
📖 Sobre o Projeto

Este projeto foi desenvolvido utilizando Python + Flask, com armazenamento de dados em arquivo usuarios.json.

O sistema começou como um CRUD básico, e evoluiu para incluir:

Autenticação com login

Regras de negócio

Segurança com hash de senha

Melhorias de UX

Controle de acesso

Contador de usuários

Atualmente o projeto está no nível:

🟡 CRUD + Autenticação + Regras de Negócio

🚀 Funcionalidades Implementadas
✅ 1. Cadastro de Usuário

O sistema permite cadastrar usuários com:

Nome

CPF

Email

Idade

Senha

🔐 Segurança

A senha não é salva em texto puro.
Foi utilizado:

generate_password_hash()

para criptografar a senha antes de salvar no JSON.

✅ 2. Regra de Negócio — Idade mínima

Foi implementada a validação:

if int(idade) < 18:

Se o usuário for menor de idade:

O cadastro não é realizado

Uma mensagem flash é exibida

✔ Resultado:
Usuário deve ser maior de idade para se cadastrar.

✅ 3. Não exibir senha na listagem

Conforme solicitado na atividade:

A senha continua salva no usuarios.json

Porém não é exibida na tabela de usuários

Antes:

Nome | CPF | Email | Idade | Senha

Depois:

Nome | CPF | Email | Idade
✅ 4. Sistema de Login

Foi criada a rota:

/login

Com formulário contendo:

CPF

Senha

No backend foi utilizado:

check_password_hash(usuario["senha"], senha_digitada)
Resultado esperado:

✔ Login válido → Flash: Login realizado com sucesso
❌ Login inválido → Flash: CPF ou senha incorretos

✅ 5. Manter dados após erro (UX)

Para melhorar a experiência do usuário, os dados digitados permanecem no formulário após erro:

value="{{ request.form.nome }}"

✔ O usuário não precisa digitar tudo novamente.

✅ 6. Contador de Usuários

Na tela de listagem foi implementado:

total = len(usuarios)

Exibindo na tela:

Total de usuários: X
📂 Estrutura do Projeto
/projeto
│
├── app.py
├── usuarios.json
├── templates/
│   ├── home.html
│   ├── cadastro-usuarios.html
│   ├── login.html
│   └── usuarios.html
│
└── static/
⚙️ Como Executar o Projeto
1️⃣ Criar ambiente virtual
python -m venv venv
2️⃣ Ativar ambiente virtual
PowerShell:
.\venv\Scripts\Activate.ps1
3️⃣ Instalar dependências
pip install flask
4️⃣ Executar aplicação
python app.py

O sistema roda em:

http://127.0.0.1:5001
🧠 Conceitos Aplicados

Flask (rotas e templates)

Renderização com Jinja2

Flash messages

Redirect e url_for

JSON como base de dados

UUID para identificação única

Hash de senha

Validação de dados

Regras de negócio

Organização de backend

📈 Evolução Técnica do Projeto

Antes:

🟢 CRUD Básico + Segurança Inicial

Depois da atividade:

🟡 CRUD + Autenticação + Regras de Negócio

👨‍💻 Autor

Marcos
Projeto desenvolvido para atividade de evolução do sistema com Flask.
