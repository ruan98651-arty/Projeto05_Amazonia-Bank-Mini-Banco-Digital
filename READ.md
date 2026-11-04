# 🏦 Amazônia Bank - Mini-Banco Digital em Terminal

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![License](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen?style=for-the-badge)

Projeto prático desenvolvido como trabalho final do módulo de **Programação Orientada a Objetos (POO)** em Python do **CETAM** (Centro de Educação Tecnológica do Amazonas).

O **Amazônia Bank** é uma aplicação de terminal que simula um sistema bancário digital completo para uma cooperativa de crédito de Manaus, com suporte a criação de contas, autenticação por senha, movimentações financeiras e persistência de dados em arquivo.

---

## 📌 Sumário

- [Visão Geral](#-visão-geral)
- [Funcionalidades](#-funcionalidades)
- [Regras de Negócio](#-regras-de-negócio)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Como Executar](#-como-executar)
- [Casos de Teste](#-casos-de-teste)
- [Conceitos Aplicados](#-conceitos-aplicados)
- [Autores](#-autores)

---

## 🎯 Visão Geral

O objetivo principal do projeto é aplicar os conceitos de **POO**, manipulação de arquivos de texto, criação de menus aninhados e validação rigorosa de dados em uma aplicação iterativa via linha de comando.

---

## ✨ Funcionalidades

- **Gerenciamento de Contas:**
  - Cadastro de novos clientes com validações de nome e senha.
  - Login seguro com validação de credenciais.
- **Operações Financeiras:**
  - Consulta de saldo formatado.
  - Depósitos e saques com validações de saldo e valores.
  - Transferências entre contas cadastradas no sistema.
  - Emissão de extrato de movimentações da sessão.
- **Persistência de Dados:**
  - Gravação automática de contas e saldos em arquivo local (`contas.txt`).
  - Carregamento de dados ao inicializar o programa.

---

## ⚙️ Regras de Negócio

1. **Titular:** Padronizado com remoção de espaços e capitalização (`title()`). Não é permitido nome vazio, uso do caractere `;` ou duplicidade de titular.
2. **Senha:** Deve conter **exatamente 4 dígitos numéricos** (`isdigit()`).
3. **Autenticação:** Acesso liberado apenas com a combinação correta de titular e senha.
4. **Movimentações:** Depósitos, saques e transferências exigem valores estritamente maiores que R$ 0,00.
5. **Saldo Insuficiente:** Não é permitido sacar ou transferir valores superiores ao saldo disponível.
6. **Transferência Segura:** A conta de destino deve existir no sistema e ser diferente da conta de origem.

---

## 📁 Estrutura do Projeto

```text
amazonia-bank/
├── projeto5_amazonia_bank.py   # Código-fonte principal do programa
├── contas.txt                  # Arquivo de persistência (gerado automaticamente)
└── README.md                   # Documentação do projeto
```

---

## 🚀 Como Executar

### Pré-requisitos
- **Python 3.8** ou superior instalado em sua máquina.

### Passos
1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/amazonia-bank.git
   ```
2. Navegue até a pasta do projeto:
   ```bash
   cd amazonia-bank
   ```
3. Execute o script principal:
   ```bash
   python projeto5_amazonia_bank.py
   ```

---

## 🧪 Quadro de Testes

Abaixo estão registrados os principais testes realizados para validação do sistema:

| ID | Cenário / Teste | Entrada Esperada | Resultado Esperado | Status |
|---|---|---|---|:---:|
| CT01 | Criar conta com nome válido e senha correta | `Nome: Marina Silva`, `Senha: 1234` | Conta criada com sucesso | ✅ |
| CT02 | Tentar senha inválida (letras) | `Senha: 12ab` | Recusa: "A senha deve ter exatamente 4 dígitos..." | ✅ |
| CT03 | Tentar cadastrar titular duplicado | `Nome: Marina Silva` | Recusa: "Já existe uma conta cadastrada..." | ✅ |
| CT04 | Depósito com valor positivo | `R$ 500.00` | Saldo atualizado para R$ 500,00 | ✅ |
| CT05 | Tentar saque maior que o saldo | `Saldo: 100.00`, `Saque: 150.00` | Recusa: "Valor inválido ou saldo insuficiente" | ✅ |
| CT06 | Transferência entre contas existentes | `Origem: 500.00`, `Destino: João`, `Valor: 200.00` | Origem: R$ 300, Destino: R$ 200 | ✅ |
| CT07 | Tentar transferir para a própria conta | `Destino: Próprio nome` | Recusa: "Não é possível transferir..." | ✅ |
| CT08 | Persistência ao reiniciar | Fechar e reabrir o programa | Saldo e dados da conta mantidos via `contas.txt` | ✅ |

---

## 🛠️ Conceitos Aplicados

- **Programação Orientada a Objetos (POO):** Classes, atributos, métodos e encapsulamento (`class Conta`).
- **Estruturas de Dados:** Manipulação de dicionários de objetos (`contas = {"Nome": objeto_conta}`).
- **Persistência de Dados:** Leitura e escrita de arquivos de texto (`open()`, `with`, `split()`).
- **Estruturas de Controle e Funções:** Laços de repetição, condicionais e modularização do código.

---

## 👥 Autores

Desenvolvido como projeto integrador final no curso de Python (CETAM).

* **Seu Nome / Nome da Dupla** - *Desenvolvimento e documentação* - [GitHub](https://github.com/seu-usuario)