
Para programar escolhemos Python que é uma linguagem de programação de alto nível, interpretada de script, imperativa, orientada a objetos, funcional, de tipagem dinâmica e forte. Foi lançada por Guido van Rossum em 1991. É uma linguagem muito fácil de aprender. Usando uma sintaxe bastante simples, ela permite explorar recursos complexos de linguagens mais complicadas (como Java e C++) com uma dificuldade muitas vezes menor.


import os
import time

lista_de_produtos = []

# Função para mostrar o menu prinpal com as  opções de validações
def menu():
    print("---------- MENU DE VALIDAÇÕES ----------")
    print("1 - Todas as letras minusculas")
    print("2 - Todas as letras maiusculas")
    print("3 - Primeiras letras maisculas")
    print("4 - Somente letras sem números")
    print("5 - Mostrar todos os produtos adicionados")
    print("\n0 - Para fechar o programa")


# Função para limpar o terminal
def limpar_terminal():
    return os.system('cls' if os.name == 'nt' else 'clear')


# Chegando se todas as letras são minusculas
def validando_minusculas():
    limpar_terminal()
    print("Validação: Somente letras minusculas")
    produto = input("Insira o produto para a validação: ").strip()

    if produto.islower():
        limpar_terminal()
        lista_de_produtos.append(produto)
        print("Produto adicionado com sucesso")
        time.sleep(3)
        limpar_terminal()
    else:
        erro_demonstracao = ""
        for letra in produto:
            if letra.isspace():
                erro_demonstracao += " "
            else:
                erro_demonstracao += "-" if letra.islower() else "^"

        print(produto)
        print(erro_demonstracao)

        print("\nO nome do produto não segue o padrão de somente só letras minusculas")
        time.sleep(3)
        limpar_terminal()
    return


# Chegando se todas as letras são maisculas
def validando_maisculas():
    limpar_terminal()

    print("Validação: Somente letras em caixa alta 'maisculas'")
    produto = input("Insira o produto para a validação: ").strip()

    if produto.isupper():
        limpar_terminal()
        print("Produto adicionado com sucess0")
        lista_de_produtos.append(produto)
        time.sleep(3)
        limpar_terminal()
    else:
        erro_demonstracao = ""

        for letra in produto:
            if letra.isspace():
                erro_demonstracao += " "
            else:
               erro_demonstracao += "-" if letra.isupper() else "^"

        print(produto)
        print(erro_demonstracao)

        print("\nO nome do produto não segue a regra de somente letras maisculas")
        time.sleep(3)
        limpar_terminal()
    return


# Chegando se a primeira letra é maiscula
def validando_primeira_letra_maiscula():
    limpar_terminal()

    print("Validação: Primeiras letras maisculas:\n")
    produto = input("Insira o produto para a validação: ")

    if produto.istitle():
        lista_de_produtos.append(produto)
        limpar_terminal()
        print("Produto adicionado com sucesso")
        time.sleep(3)
        limpar_terminal()
    else:
        print("Palavra que não começam com uma letra maiuscula")

        palavras = produto.strip().split(' ')

        erro_demostracao = ""

        for palavra in palavras:

            if not palavra.istitle():
                erro_demostracao += "^"
                erro_demostracao += "-" * (len(palavra) - 1)
                erro_demostracao += " "

            else:
                erro_demostracao += "-" * len(palavra)
                erro_demostracao += " "

        print(produto)
        print(erro_demostracao)
        time.sleep(3)
        limpar_terminal()

    return


# Checando se só a letras sem números
def validando_somente_letras():
    limpar_terminal()

    print("Validação: Somente letras:\n")
    produto = input("Insira o produto para a validação: ").strip()

    if produto.replace(' ', '').isalpha():
        lista_de_produtos.append(produto)
        limpar_terminal()
        print("Produto adicionado com sucesso")
        limpar_terminal()
        time.sleep(3)
    else:
        erro_demonstracao = ""
        
        for letra in produto:
            if letra.isspace():
                erro_demonstracao += " "
            
            else:    
                if letra.isnumeric():
                    erro_demonstracao += "^"
                else:
                    erro_demonstracao += "-"

        print("\nEncontrado números nas palavras")
        print(produto)
        print(erro_demonstracao)
        print("\nO nome do produto não segue as regras de ter somente letras")
        time.sleep(3)
        limpar_terminal()

    return    


# Mostrando todos os produtos
def mostrar_produtos():
    limpar_terminal()
    if len(lista_de_produtos) > 0:
        for produto in lista_de_produtos:
            print(produto)
    else:
        print("sem produtos cadastrados")
    
    time.sleep(3)
    limpar_terminal()
    return



def main():
    options = [
        validando_minusculas,
        validando_maisculas,
        validando_primeira_letra_maiscula,
        validando_somente_letras,
        mostrar_produtos
    ]

    opc = -1

    while(True):
        menu()  
        try:
            opc = int(input())

            if opc == 0:
                limpar_terminal()
                print("Programa encerrado")
                break
            
            if opc < 0 or opc > 5:
                limpar_terminal()
                print("Por favor insira uma opção válida na próxima vez.")
                time.sleep(3)
                limpar_terminal()
            else:
                options[opc - 1]()
        except:  
            limpar_terminal()
            print("Ops por favor somente números sem letras")
            time.sleep(3)
            continue

        
    return

main()
