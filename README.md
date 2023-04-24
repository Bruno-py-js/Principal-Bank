# Principal-Bank
Um desafio de criação!! 
class Banco:
    def __init__(self):
        self.saldo = 0
        self.saque_permitido = 1000

    def depositar(self, valor):
        self.saldo += valor

    def sacar(self, valor):
        if self.saldo - valor >= 0 and valor <= self.saque_permitido:
            self.saldo -= valor
            print("Saque realizado com sucesso!")
        else:
            print("Não foi possível realizar o saque.")

    def extrato(self):
        print(f"Saldo atual: {self.saldo}")
        print(f"Saque permitido: {self.saque_permitido}")

#Este código define uma classe Banco que possui três métodos principais: depositar, sacar e extrato. O método depositar adiciona um valor ao saldo do banco, enquanto o método sacar retira um u permitido. O método extrato imprime o saldo atual e a quantidavalor do saldo do banco se o valor for menor ou igual ao limite de saqde de saque permitido.e

import getpass

usuario = input("Digite seu usuário: ")
senha = getpass.getpass("Digite sua senha: ")
#Com isso, você pode solicitar o usuário e a senha do usuário sem exibir a senha na tela.

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:
    print("========menu=======")
    print("[1] Depositar")
    print("[2] Sacar")
    print("[3] Extrato")
    print("[0] Sair")
    print("=====Bem vindo=====")

    opcao = input("=> ")

    if opcao == "1":
        valor = float(input("Informe o valor a ser depositado: "))
        saldo += valor
        print(f"Depósito de R${valor:.2f} realizado com sucesso!")
    elif opcao == "2":
        if numero_saques >= LIMITE_SAQUES:
            print("Limite de saques atingido.")
        else:
            valor = float(input("Informe o valor a ser sacado: "))
            if valor > saldo:
                print("Saldo insuficiente.")
            elif valor > limite:
                print(f"Valor máximo de saque permitido é de R${limite:.2f}.")
            else:
                saldo -= valor
                numero_saques += 1
                print(f"Saque de R${valor:.2f} realizado com sucesso!")
    elif opcao == "3":
        print(f"Saldo atual: R${saldo:.2f}")
        print(f"Limite de saque: R${limite:.2f}")
        print(f"Número de saques realizados: {numero_saques}")
    elif opcao == "0":
        break
    else:
        print("Operação inválida. Por favor selecione novamente a operação desejada.")
