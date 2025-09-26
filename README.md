# 🍔 Sistema de Gerenciamento de Pedidos

## 👥 Equipe
- Membro 1: Asafe Dórea de Oliveira Arêas
- Membro 2: Emmerson Sobrinho
- Membro 3: Edmilson Bastos
- Membro 4: Anderson Antonio
- Membro 5: Gabriel de Oliveira Queiroz

---

## 📖 Descrição
Este projeto é um sistema de gerenciamento de pedidos desenvolvido em **Python**, rodando diretamente no terminal.  
O objetivo é simular o funcionamento básico de um restaurante, utilizando apenas **estruturas de dados nativas** (listas) para representar clientes, itens, pedidos e filas de processamento.

O sistema é totalmente interativo via linha de comando, permitindo cadastrar clientes, gerenciar itens do cardápio e controlar o fluxo de pedidos desde a criação até a entrega.

---

## ⚙️ Estrutura e Funcionalidades

### 🔹 Gerenciar Clientes
- **Cadastrar Cliente**: Adiciona um novo cliente com ID gerado automaticamente.  
- **Listar Clientes**: Exibe todos os clientes cadastrados.  

### 🔹 Gerenciar Menu de Itens
- **Cadastrar Item**: Adiciona um novo produto ao cardápio.  
- **Consultar Itens**: Lista todos os itens cadastrados com descrição, preço e estoque.  
- **Atualizar Item**: Permite alterar nome, descrição, preço e quantidade em estoque.  
- **Excluir Item**: Remove permanentemente um item do cardápio.  

Cada item é armazenado com as seguintes informações:  
- `código`: Identificador único (gerado automaticamente).  
- `nome`: Nome do produto.  
- `descrição`: Detalhes sobre o item.  
- `preço`: Valor monetário.  
- `estoque`: Quantidade disponível.  

### 🔹 Gerenciar Pedidos
- **Criar Pedido**:
  - Seleciona cliente existente ou cadastra rapidamente um novo.  
  - Adiciona um ou mais itens (respeitando o estoque).  
  - Possibilidade de aplicar desconto percentual via cupom.  
  - Pedido inicia com status `AGUARDANDO_APROVACAO`.  

- **Cancelar Pedido**:  
  - Só permitido quando o pedido está em `AGUARDANDO_APROVACAO` ou `ACEITO`.  
  - Estoque é devolvido se já tiver sido reservado.  

- **Processar Pedidos Pendentes**:  
  - Analisa pedidos em fila (FIFO).  
  - Opções: aceitar (estoque é reservado), rejeitar ou pular.  

- **Atualizar Status de Pedido**:  
  - Permite transições manuais no fluxo (FAZENDO → FEITO → ESPERANDO ENTREGADOR → ENTREGA).  

- **Consultar Pedidos**:  
  - Exibe todos os pedidos cadastrados com seus detalhes.  
  - Possibilidade de filtrar por status específico.  

---

## 🔹 Fluxo de Pedidos e Filas
O sistema utiliza **filas FIFO** para gerenciar o ciclo de vida dos pedidos:

- **Fila de Pendentes**: todos os novos pedidos entram aqui.  
- **Fila de Aceitos**: pedidos aceitos e em preparo (status `FAZENDO`).  
- **Fila de Prontos**: pedidos finalizados no preparo, aguardando entregador (`ESPERANDO ENTREGADOR`).  

---

## 🔹 Fluxo de Status
Os pedidos podem assumir os seguintes status:

- `AGUARDANDO_APROVACAO`  
- `ACEITO`  
- `FAZENDO`  
- `FEITO`  
- `ESPERANDO ENTREGADOR`  
- `SAIU PARA ENTREGA`  
- `ENTREGUE`  
- `CANCELADO`  
- `REJEITADO`  

---

## 🔹 Relatórios
O sistema também oferece relatórios básicos:
- Total faturado com pedidos entregues.  
- Quantidade de pedidos agrupados por status.  
- Ranking dos itens mais vendidos.  

---

## 🛠️ Tecnologias Utilizadas
- **Python 3.x**  
- **Listas** como principal estrutura de dados  
- **Interface via terminal (CLI)**  

---

## ▶️ Como Executar
1. Clone o repositório:
   ```bash
   git clone https://github.com/usuario/repositorio.git
   cd repositorio
