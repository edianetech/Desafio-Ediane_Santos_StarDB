# Desafio-Ediane_Santos_StarDB

// Definindo o cardápio com os itens e seus preços
const cardapio = {
  cafe: 3.00,
  chantily: 1.50,
  suco: 6.20,
  sanduiche: 6.50,
  queijo: 2.00,
  salgado: 7.25,
  combo1: 9.50,
  combo2: 7.50
};

// Função para calcular o valor total da compra
function calcularValorDaCompra(itensSelecionados, metodoPagamento) {
  let total = 0;

  // Iterar sobre os itens selecionados e somar os preços
  for (const item of itensSelecionados) {
    total += cardapio[item] || 0;
  }

  // Aplicar desconto ou acréscimo com base no método de pagamento
  if (metodoPagamento === 'dinheiro') {
    total *= 0.95; // Aplicar 5% de desconto
  } else if (metodoPagamento === 'credito') {
    total *= 1.03; // Aplicar 3% de acréscimo
  }

  return total;
}


const itensSelecionados = ['cafe', 'sanduiche', 'queijo'];
const metodoPagamento = 'dinheiro'; // ou 'credito'

const valorTotal = calcularValorDaCompra(itensSelecionados, metodoPagamento);

console.log(`Valor total da compra: R$ ${valorTotal.toFixed(2)}`);

