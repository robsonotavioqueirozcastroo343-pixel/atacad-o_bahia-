#include <stdio.h>
#include <string.h>

#define MAX 100
   
// ESTRUTURA DO PRODUTO
   
typedef struct {
    char nome[50];
    float preco;
    int quantidade;
} Produto;

Produto produtos[MAX];
int totalProdutos = 0;


   
// Função para adicionar produto
   
void adicionarProduto() {

    if (totalProdutos >= MAX) {
        printf("Limite máximo de produtos atingido!\n");
        return;
    }

    printf("\n--- Cadastro de Produto ---\n");

    printf("Nome: ");
    scanf(" %[^\n]", produtos[totalProdutos].nome);

    printf("Preço: ");
    scanf("%f", &produtos[totalProdutos].preco);

    printf("Quantidade: ");
    scanf("%d", &produtos[totalProdutos].quantidade);

    totalProdutos++;

    printf("\nProduto cadastrado com sucesso!\n\n");
}

//  Aplicar desconto baseado no tipo

float aplicarDescontoPorTipo(float total, int tipoProduto) {
    float desconto = 0;

    switch (tipoProduto) {
        case 1: // Doces
            if (total >= 200) desconto = total * 0.05;
            break;

        case 2: // Temperos
            if (total >= 150) desconto = total * 0.10;
            break;

        case 3: // Verduras
            if (total >= 200) desconto = total * 0.10;
            break;

        case 4: // Outros
            if (total >= 150) desconto = total * 0.05;
            break;

        default:
            printf("Tipo inválido, sem desconto.\n");
    }

    return desconto;
}

//  Calcular total dos produtos
   
float calcularTotal() {
    float total = 0;

    for (int i = 0; i < totalProdutos; i++) {
        total += produtos[i].preco * produtos[i].quantidade;
    }

    return total;
}


   
//   Emitir nota fiscal
   
void emitirNotaFiscal() {

    if (totalProdutos == 0) {
        printf("\nNenhum produto cadastrado!\n\n");
        return;
    }

    printf("\n--- NOTA FISCAL ---\n");

    for (int i = 0; i < totalProdutos; i++) {
        printf("%d. %s - R$ %.2f x %d = R$ %.2f\n",
               i + 1,
               produtos[i].nome,
               produtos[i].preco,
               produtos[i].quantidade,
               produtos[i].preco * produtos[i].quantidade);
    }

    float total = calcularTotal();
    int tipoProduto;

    printf("\nInforme o tipo do produto para aplicar desconto:\n");
    printf("1 - Doces\n");
    printf("2 - Temperos\n");
    printf("3 - Verduras\n");
    printf("4 - Outros\n");
    printf("Opção: ");
    scanf("%d", &tipoProduto);

    float desconto = aplicarDescontoPorTipo(total, tipoProduto);
    float totalFinal = total - desconto;

    printf("\nTOTAL: R$ %.2f\n", total);
    printf("DESCONTO: R$ %.2f\n", desconto);
    printf("TOTAL FINAL: R$ %.2f\n", totalFinal);
    printf("-------------------------\n\n");
}


   
// MENU FINAL
   
void menu() {
    int opcao;

    do {
        printf("\n===== Mercado do Zé - C =====\n");
        printf("1. Adicionar Produto\n");
        printf("2. Emitir Nota Fiscal\n");
        printf("3. Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &opcao);

        switch (opcao) {
            case 1: adicionarProduto(); break;
            case 2: emitirNotaFiscal(); break;
            case 3: printf("Programa encerrado!\n"); break;
            default: printf("Opção inválida!\n");
        }

    } while (opcao != 3);
}
   
// PROGRAMA PRINCIPAL
   
int main() {
    menu();
    return 0;
}
