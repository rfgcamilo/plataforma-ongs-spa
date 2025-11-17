# Plataforma ONGs – SPA em JavaScript

Projeto desenvolvido como **3ª entrega** da disciplina de **Desenvolvimento Front-End Para Web**.

O objetivo é transformar uma interface estática em uma **aplicação web dinâmica e interativa**, utilizando **JavaScript avançado**, com:

- Sistema básico de **Single Page Application (SPA)**  
- **Templates em JavaScript** para montagem das telas  
- **Manipulação de DOM** e eventos  
- **Validação de formulários** com avisos de preenchimento incorreto  
- Uso de **`localStorage`** para simular persistência de dados  

---

## 🧩 Contexto do Projeto

O projeto simula uma **plataforma para ONGs** do terceiro setor, permitindo:

- Divulgar projetos sociais
- Cadastrar voluntários em um formulário com validação
- Listar voluntários cadastrados (dados simulados via `localStorage`)

> Este é um projeto **acadêmico**, sem fins comerciais, criado para demonstrar o uso integrado de HTML5, CSS3 e JavaScript modular.

---

## 🚀 Funcionalidades Principais

### 1. Single Page Application (SPA)

- Navegação entre seções via **hash na URL** (`#home`, `#projetos`, `#voluntarios`)
- Arquivo responsável: `assets/js/router.js`
- O conteúdo visível é sempre renderizado dentro da `<main id="app"></main>`

### 2. Sistema de Templates em JavaScript

- As “telas” da aplicação são criadas via funções JavaScript que retornam elementos DOM:
  - `createHomeView()`
  - `createProjetosView()`
  - `createVoluntariosView()`
- Arquivo responsável: `assets/js/templates.js`

### 3. Manipulação do DOM e Eventos

- Renderização dinâmica de conteúdo com `innerHTML` e criação de elementos com `document.createElement`
- Escuta de eventos:
  - `hashchange` → para troca de rota (SPA)
  - `submit` → para validação de formulários

### 4. Validação de Formulário (Consistência de Dados)

Formulário de **Cadastro de Voluntário** com:

- Campos obrigatórios validados (`data-required="true"`)
- Validação de:
  - Nome (tamanho mínimo)
  - E-mail (formato correto)
  - Confirmação de e-mail (`data-match="#email"`)
  - Telefone (quantidade mínima de dígitos)
  - Área de interesse (select obrigatório)
  - Disponibilidade numérica (faixa mínima/máxima)
- Exibição de:
  - Mensagens de erro por campo (`.error-message`)
  - Destaque visual de campos inválidos (`.field-error`)
  - Mensagem geral de erro ou sucesso acima do formulário

Arquivo responsável: `assets/js/validation.js`

### 5. Armazenamento Local (`localStorage`)

- Voluntários cadastrados são salvos no navegador via `localStorage`
- Os dados são carregados posteriormente na seção **Projetos**, simulando uma listagem de voluntários interessados.

Arquivo responsável: `assets/js/storage.js`

---

## 🗂 Estrutura de Pastas

```text
/
├── index.html
├── assets
│   ├── css
│   │   └── style.css
│   ├── img
│   │   └── (imagens da aplicação)
│   └── js
│       ├── app.js          # Ponto de entrada da aplicação
│       ├── router.js       # Sistema de rotas (SPA)
│       ├── templates.js    # Templates das views/telas
│       ├── validation.js   # Sistema de validação de formulários
│       └── storage.js      # Leitura/Gravação em localStorage
