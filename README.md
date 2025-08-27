# Projeto-Calculadora-de-despesas
Criar uma calculadora onde vou inserindo os gastos ao longo do mês e para manter o controle das despesas e poder visualizar o relatório do que foi gasto atualmente

# Funcionalidades
Adicionar novas despesas (com descrição e valor).

Exibir a lista de despesas cadastradas.

Mostrar o total gasto automaticamente.

Interface simples e responsiva para uso em computador ou celular.

# Tecnologias Utilizadas
HTML5 → estrutura da aplicação.

CSS3 → estilização e design responsivo.

JavaScript → lógica para calcular e atualizar as despesas em tempo real.

# Como executar o projeto



<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora de Despesas</title>
  <style>
    /* === Estilo geral === */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f4f6f8;
      color: #333;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .container {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      width: 90%;
      max-width: 500px;
    }

    h1 {
      text-align: center;
      color: #2c3e50;
    }

    /* === Formulário === */
    form {
      display: flex;
      flex-direction: column;
      gap: 10px;
      margin-bottom: 20px;
    }

    input, button {
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ddd;
      border-radius: 8px;
    }

    input:focus {
      outline: none;
      border-color: #2980b9;
    }

    button {
      background: #2980b9;
      color: #fff;
      border: none;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #1f5f87;
    }

    /* === Lista de despesas === */
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    li {
      display: flex;
      justify-content: space-between;
      padding: 10px;
      margin-bottom: 8px;
      background: #f9f9f9;
      border-radius: 8px;
      border: 1px solid #eee;
    }

    /* === Total === */
    .total {
      text-align: center;
      font-size: 20px;
      font-weight: bold;
      margin-top: 15px;
      color: #27ae60;
    }

    /* Responsividade */
    @media (max-width: 600px) {
      .container {
        padding: 15px;
      }
      input, button {
        font-size: 14px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>💰 Calculadora de Despesas</h1>
    
    <!-- Formulário para adicionar despesas -->
    <form id="expense-form">
      <input type="text" id="description" placeholder="Descrição da despesa" required>
      <input type="number" id="amount" placeholder="Valor (R$)" required min="0.01" step="0.01">
      <button type="submit">Adicionar</button>
    </form>

    <!-- Lista de despesas -->
    <ul id="expense-list"></ul>

    <!-- Total gasto -->
    <div class="total">Total Gasto: R$ <span id="total">0.00</span></div>
  </div>

  <script>
    const form = document.getElementById("expense-form");
    const descriptionInput = document.getElementById("description");
    const amountInput = document.getElementById("amount");
    const expenseList = document.getElementById("expense-list");
    const totalDisplay = document.getElementById("total");

    let total = 0;

    form.addEventListener("submit", function(event) {
      event.preventDefault();

      const desc

