saldo= 8000 
numero_saque=0
limite_saque=3
extrato= ""

while True:
    opcoes= int( input("[1] DEPOSITO \\ [2] SAQUE\\ [3] EXTRATO"))
    if opcoes not in [1,2,3]:
        print("insira um valor válido")
        continue

    #DEPOSITO
    if opcoes ==1:
        solic_deposito=int(input("Selecione o valor que deseja depositar e insira as cedulas"))
        if solic_deposito >=5:
            extrato+= f"Deposito R$ +{solic_deposito:.2f}\n"
            saldo+=solic_deposito
            valor_deposito = solic_deposito
            print(f"Deposito de R${solic_deposito} feito com sucesso")
            print("Obrigado por utilizar os nossos serviços !!")
            saida=int(input(" [1] retornar as opções\\ [2] sair"))
            if saida ==1:
                print(opcoes)
            elif saida == 2:
                break
        else:
            print("Valor minimo de deposito é de R$ 5 reais")
            continue

        #SAQUE
    if opcoes ==2:
        if numero_saque >=limite_saque:
            print("Limite de saques diarios atingidos")
            continue
            
        else:
            valor_saque=int(input("Qual o valor do saque ?"))
        
        if valor_saque >500:
            print("o limite é de R$ 500 reais por saque")
        elif valor_saque > saldo:
            print(f"saldo insuficiente")
        else:
            numero_saque+=1
            extrato+=f"Saque - R$ {valor_saque:.2f} \n"
            saldo -=valor_saque
            print(f"saque de R${valor_saque} realizado com sucesso! ")
            print("Obrigado por utilizar os nossos serviços !!")
        saida=int(input(" [1] retornar as opções\\ [2] sair"))
        if saida ==1:
            print(opcoes)
        elif saida == 2:
            break
    if opcoes ==3:
        print(f"=======EXTRATO=======")
        if extrato == "":
            print(" Nenhuma operação realizada")
        else:
            print(saldo)

            print(extrato)

            print("Obrigado por utilizar os nossos serviços !!")
            saida=int(input(" [1] retornar as opções\\ [2] sair"))
            if saida ==1:
                print(opcoes)
            elif saida == 2:
                break    
