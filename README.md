![image](https://github.com/DalilaDeveloperMobile/Criando-Sistema-Bancario-Python/assets/29806802/88dcdc9d-d4ca-4f63-866b-6f3497d87e1d)
### Passos Realizados Nesse Bootcamp Python AI Backend Developer. [dio_me](https://www.dio.me/)
### ✅Criando um Sistema Bancário com Python.

### <img src="https://gifs.eco.br/wp-content/uploads/2021/06/gifs-de-coracao-7.gif" width="30px"> Sistema Bancário Python:

```
menu = """

   =============== MENU ===============

     [1] Depositar
     [2] Sacar
     [3] Extrato
     [4] Sair

    ===================================

=> """

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)

    if opcao == "1":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"

        else:
            print("Operação falhou! o valor informado é inválido.")                

    elif opcao == "2":
        valor = float(input("Informe o valor do saque: ")) 

        excedeu_saldo = valor > saldo

        excedeu_limite = valor > limite

        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou! o valor do saque excede o limite.")

        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedido.")    
    
        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1

        else:
            print("Operação falhou! O valor informado é inválido.")    

    elif opcao == "3":
        print("\n===========Extrato===========")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo R$ {saldo:.2f}")
        print("==============================")
        
    elif opcao == "4":
        break    

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")
```

