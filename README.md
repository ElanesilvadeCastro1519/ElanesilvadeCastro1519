class Produto:
    def __init__(self, nome, quantidade):
        self.nome = nome
        self.quantidade = quantidade

    def __str__(self):
        return f"{self.nome}: {self.quantidade}"

class Estoque:
    def __init__(self):
        self.produtos = []

    def adicionar_produto(self, produto):
        self.produtos.append(produto)

    def remover_produto(self, nome):
        for produto in self.produtos:
            if produto.nome == nome:
                self.produtos.remove(produto)
                break

    def atualizar_quantidade(self, nome, quantidade):
        for produto in self.produtos:
            if produto.nome == nome:
                produto.quantidade += quantidade
                break

    def __str__(self):
        resultado = ""
        for produto in self.produtos:
            resultado += str(produto) + "\n"
        return resultado

estoque = Estoque()
estoque.adicionar_produto(Produto("Camiseta", 10))
estoque.adicionar_produto(Produto("Calça", 5))
estoque.adicionar_produto(Produto("Sapato", 3))

print(estoque)

estoque.atualizar_quantidade("Camiseta", -2)
estoque.atualizar_quantidade("Calça", 1)

print(estoque)

estoque.remover_produto("Sapato")

print(estoque)
