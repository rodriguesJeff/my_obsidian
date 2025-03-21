

---

# 📋 ToDo - Desafio Técnico Flutter (UEX Tecnologia)

## 🔖 Módulo 1: Autenticação de Usuário

### Cadastro (Sign Up)

- [x]  Criar tela de cadastro de usuário
- [x]  Implementar campos obrigatórios:
    - [x]  Nome completo
    - [x]  E-mail
    - [x]  Senha
- [x]  Validação de:
    - [x]  E-mail único (não permitir e-mails repetidos)
- [x]  Armazenar usuário no banco local (SharedPreferences, SQLite ou LocalStorage)
- [x]  Feedback de sucesso/erro no cadastro

### Login (Sign In)

- [x]  Criar tela de login
- [x]  Autenticação por e-mail e senha
- [x]  Verificar credenciais com dados do banco local
- [x]  Feedback de sucesso/erro no login

### Logout

- [ ]  Criar função de logout
- [ ]  Redirecionar usuário para tela de login ao deslogar
- [ ]  Limpar sessão do usuário logado

### Autorização

- [ ]  Bloquear acesso às telas de contatos sem login
- [ ]  Redirecionar para tela de login se o usuário não estiver autenticado

---

## 📒 Módulo 2: Gerenciamento de Contatos

### Cadastro de Contato

- [ ]  Criar tela de cadastro de contatos
- [x]  Campos obrigatórios:
    - [x]  Nome completo
    - [ ]  CPF (com validação oficial)
    - [x]  Telefone
    - [x]  Endereço completo:
        - [x]  CEP
        - [x]  UF
        - [x]  Cidade
        - [x]  Logradouro
        - [x]  Número
        - [x]  Complemento (opcional)
    - [ ]  Latitude e Longitude (via Google Maps)
- [ ]  Validações:
    - [ ]  CPF válido
    - [ ]  Não permitir CPF duplicado para o usuário logado
- [ ]  Salvar contato no banco de dados local

### Edição de Contato

- [ ]  Criar tela/modal para editar contato existente
- [ ]  Carregar dados existentes no formulário
- [ ]  Validar CPF em caso de alteração
- [ ]  Atualizar dados no banco local

### Exclusão de Contato

- [ ]  Criar opção para excluir um contato da lista
- [ ]  Confirmar exclusão com o usuário
- [ ]  Remover contato do banco local

### Listagem de Contatos

- [ ]  Exibir lista de contatos ordenada por nome (A-Z)
- [ ]  Permitir reordenação da lista (Z-A, outros critérios)
- [ ]  Implementar filtro:
    - [ ]  Por nome
    - [ ]  Por CPF
- [ ]  Quando um contato for selecionado:
    - [ ]  Centralizar e marcar no mapa com “pin” a coordenada (latitude/longitude)

---

## 🗺️ Módulo 3: Integração Via CEP e Google Maps

### Busca por Endereço (Via CEP)

- [ ]  Criar widget de busca de endereços usando a API ViaCEP
- [ ]  Usuário digita:
    - [ ]  UF
    - [ ]  Cidade
    - [ ]  Trecho do endereço
- [ ]  Exibir lista de sugestões de endereços
- [ ]  Preencher automaticamente os campos do formulário de endereço ao selecionar item da lista

### Coordenadas Geográficas (Google Maps)

- [ ]  Obter latitude e longitude automaticamente com base no endereço informado
- [ ]  Exibir marcador no mapa do contato selecionado
- [ ]  Integrar Google Maps para mostrar o local dos contatos cadastrados
- [ ]  Centralizar mapa no contato clicado na lista

---

## ❌ Módulo 4: Exclusão de Conta

### Excluir Conta do Usuário

- [ ]  Criar tela/modal para confirmação de exclusão de conta
- [ ]  Solicitar senha para confirmar ação
- [ ]  Validar senha
- [ ]  Remover conta e todos os dados associados (contatos) do banco local
- [ ]  Redirecionar para tela de login após exclusão

---

## 🎨 Módulo 5: UI/UX e Design System

- [ ]  Adotar Material Design V2 ou V3 em todas as telas
- [ ]  Mensagens de feedback (Snackbars, Alerts)
- [ ]  Formulários com validações visuais (erro, sucesso)
- [ ]  Garantir responsividade para resoluções mínimas de 1366x768
- [ ]  Melhorar a UX de navegação entre telas (Animações, Transições)

---

## 📝 Módulo 6: Infraestrutura e Boas Práticas

- [ ]  Estruturar o projeto com design pattern (exemplo: MVVM, Clean Architecture, etc.)
- [ ]  Garantir código limpo e comentado
- [ ]  Seguir boas práticas de versionamento no Git
- [ ]  Evitar dados hardcoded (usuários/contatos devem ser dinâmicos)
- [ ]  Persistir os dados localmente sem se perder ao atualizar a tela (F5)
- [ ]  Garantir persistência com SQLite ou outra tecnologia local
- [ ]  Preparar para deploy em Flutter Web, Windows ou Android

---

## ✅ Checklist Final

- [ ]  Todos os requisitos obrigatórios implementados
- [ ]  Testes manuais realizados
- [ ]  Repositório Git organizado
- [ ]  README.md com instruções de execução e informações do projeto
- [ ]  Apresentação agendada com a equipe da UEX

---