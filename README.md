#  Desenvolvimento de Funcionalidade de Validação do Sistema de  supermercado usando python . Python é uma linguagem de programação de alto nível, interpretada de script, imperativa, orientada a objetos, funcional, de tipagem dinâmica e forte. Foi lançada por Guido van Rossum em 1991. É uma linguagem muito fácil de aprender. Usando uma sintaxe bastante simples, ela permite explorar recursos complexos de linguagens mais complicadas (como Java e C++) com uma dificuldade muitas vezes menor.

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
   
   import time
import functions


def main():
    options = [
        functions.validando_minusculas,
        functions.validando_maisculas,
        functions.validando_primeira_letra_maiscula,
        functions.validando_somente_letras,
        functions.mostrar_produtos
    ]

    opc = -1

    while(True):
        functions.menu()  
        try:
            opc = int(input())

            if opc == 0:
                functions.limpar_terminal()
                print("Programa encerrado")
                break
            
            if opc < 0 or opc > 5:
                functions.limpar_terminal()
                print("Por favor insira uma opção válida na próxima vez.")
                time.sleep(3)
                functions.limpar_terminal()
            else:
                options[opc - 1]()
        except:  
            functions.limpar_terminal()
            print("Ops por favor somente números sem letras")
            time.sleep(3)
            continue

        
    return

main()


def validateEmail(email):
 if len(email) <= 64:
  print("email Correto")
  return True
 else:
  print("email Incorreto")
  return False
  
if (email)[0] >= '0' and (email)[0] <= '9':
   print("O primeiro caracter do e-mail é numérico")
else:
  print("O primeiro caracter do e-mail NÃO é numérico")

email= input(print("utiliza caracteres?: "))
def validateEmail(email):
 if len(email) <= 255:
  print("email tem ate 255 caracteres")
  return True
 else:
  print("email tem mais de 255 caracters")
  return False
 if int() <=63:
  print("as etiquetas contém até 63 caracter")
  return True
 else:
  print("as etiquetas tem mais de 63 caracter")
  return False

while True:
 email=input("Digite uma String:")
 if texto.insupper():
  print("Tudo maiúsculo")
 elif texto.islower():
  print("Tudo minúsculo")
 else:
  print("misturado")
     # TODO: write code...

import string
a = list(string.ascii_lowercase)

print ("a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z")


cpf = "20415020324"
cpf = str(cpf)
tamanho_cpf = len(cpf)
print(tamanho_cpf)

class Cpf:
    def cpf_valido(self,documento):
     cpf = input ("Digite seu cpf");
     if len(cpf) == 11:
            print("CPF válido")
            return True 
     else:
            print("CPF inválido")
            return False

cnpj = "23382736567362"
cnpj = str(cnpj)
tamanho_cnpj = len(cnpj)
print(tamanho_cnpj)

class Cnpj:
    def cnpj_valido(self,documento):
     cnpj = input ("Digite seu cnpj");
     if len(cnpj) == 14:
            print("CNPJ válido")
            return True 
     else:
            print("CNPJ inválido")
            return False
    
    
    
