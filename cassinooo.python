import random
import time

class UsuarioDoCassino:
    def __init__(self, nome, idade, saldo, senha):
        self.nome = nome
        self.idade = idade
        self.saldo = saldo
        self.senha = senha

    def mostrar(self):
        print(f"Nome: {self.nome}")
        print(f"Idade: {self.idade}")
        print(f"Saldo: R$ {self.saldo:.2f}")
        print("=" * 30)

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            print(f"Depósito de R$ {valor:.2f} realizado com sucesso!")
            print(f"Saldo atual: R$ {self.saldo:.2f}")
        else:
            print("Valor inválido para depósito.")
        print("=" * 30)

    def verificar_senha(self, senha):
        return self.senha == senha

    def apostar(self, valor):
        if valor <= 0:
            print("Valor de aposta inválido.")
            return False
        if valor > self.saldo:
            print("Saldo insuficiente para essa aposta.")
            return False
        self.saldo -= valor
        return True

    def ganhar(self, valor):
        self.saldo += valor

def blackjack(usuario):
    print("\n--- Blackjack ---")
    while True:
        print("Escolha uma opção:")
        print("1. Receber cartas")
        print("2. Passar")
        print("3. Apostar dinheiro")
        print("4. Sair do Blackjack")
        opcao = input("Digite a opção desejada: ")

        if opcao == "1":
            cartas = list(range(1, 14)) * 4  # Baralho simplificado
            random.shuffle(cartas)
            carta1 = cartas.pop()
            carta2 = cartas.pop()
            soma = carta1 + carta2
            print(f"Você tirou {carta1} e {carta2}. Soma: {soma}")

            if soma == 21:
                print("Blackjack! Você ganhou!")
                # Exemplo: ganha 2x a aposta (não implementado aposta aqui)
            else:
                print("Você não fez Blackjack.")
            # Perguntar se quer continuar
            continuar = input("Deseja continuar jogando Blackjack? (s/n): ").lower()
            if continuar != 's':
                break

        elif opcao == "2":
            print("Você passou a vez no Blackjack.")
            break

        elif opcao == "3":
            valor = float(input("Digite o valor que deseja apostar: R$ "))
            if usuario.apostar(valor):
                cartas = list(range(1, 14)) * 4
                random.shuffle(cartas)
                carta1 = cartas.pop()
                carta2 = cartas.pop()
                soma = carta1 + carta2
                print(f"Você tirou {carta1} e {carta2}. Soma: {soma}")
                if soma == 21:
                    premio = valor * 2
                    usuario.ganhar(premio)
                    print(f"Parabéns! Você ganhou R$ {premio:.2f}!")
                else:
                    print("Você perdeu a aposta.")
                print(f"Saldo atual: R$ {usuario.saldo:.2f}")
            else:
                print("Não foi possível realizar a aposta.")
        elif opcao == "4":
            print("Saindo do Blackjack.")
            break
        else:
            print("Opção inválida. Tente novamente.")

def roulette(usuario):
    print("\n--- Roleta ---")
    dinheiro = 0
    while True:
        print("Escolha uma opção:")
        print("1. Girar a roleta")
        print("2. Apostar dinheiro")
        print("3. Sair da Roleta")
        opcao = input("Digite a opção desejada: ")

        if opcao == "1":
            emogis = ["🍎", "🍒", "🍉"]
            # Animação simples
            for _ in range(10):
                print("".join(random.choices(emogis, k=3)), end="\r")
                time.sleep(0.1)
            resultado = random.choices(emogis, k=3)
            print(f"Resultado: {' '.join(resultado)}")
            if resultado[0] == resultado[1] == resultado[2]:
                print("Você ganhou!")
                if dinheiro > 0:
                    premio = dinheiro * 3
                    usuario.ganhar(premio)
                    print(f"Você ganhou R$ {premio:.2f}!")
                else:
                    print("Mas você não apostou dinheiro.")
            else:
                print("Você não ganhou dessa vez.")
            print(f"Saldo atual: R$ {usuario.saldo:.2f}")

        elif opcao == "2":
            dinheiro = float(input("Digite o valor que deseja apostar: R$ "))
            if usuario.apostar(dinheiro):
                print(f"Aposta de R$ {dinheiro:.2f} realizada com sucesso!")
            else:
                dinheiro = 0  # aposta inválida
            print(f"Saldo atual: R$ {usuario.saldo:.2f}")

        elif opcao == "3":
            print("Saindo da Roleta.")
            break
        else:
            print("Opção inválida. Tente novamente.")

def poker(usuario):
    print("\n--- Poker ---")
    dinheiro = 0
    while True:
        print("Escolha uma opção:")
        print("1. Embaralhar e receber cartas")
        print("2. Apostar dinheiro")
        print("3. Sair do Poker")
        opcao = input("Digite a opção desejada: ")

        if opcao == "1":
            cartas = list(range(1, 14)) * 4
            random.shuffle(cartas)
            mao = [cartas.pop() for _ in range(5)]
            print(f"Suas cartas: {mao}")
            # Condição simples de vitória: todas as cartas iguais (muito improvável)
            if len(set(mao)) == 1:
                print("Você ganhou!")
                if dinheiro > 0:
                    premio = dinheiro * 5
                    usuario.ganhar(premio)
                    print(f"Você ganhou R$ {premio:.2f}!")
                else:
                    print("Mas você não apostou dinheiro.")
            else:
                print("Você não ganhou dessa vez.")
            print(f"Saldo atual: R$ {usuario.saldo:.2f}")

        elif opcao == "2":
            dinheiro = float(input("Digite o valor que deseja apostar: R$ "))
            if usuario.apostar(dinheiro):
                print(f"Aposta de R$ {dinheiro:.2f} realizada com sucesso!")
            else:
                dinheiro = 0
            print(f"Saldo atual: R$ {usuario.saldo:.2f}")

        elif opcao == "3":
            print("Saindo do Poker.")
            break
        else:
            print("Opção inválida. Tente novamente.")

def main():
    usuarios = {}  # dicionário para armazenar usuários cadastrados

    print("Bem-vindo ao cassino!")
    while True:
        print("\nEscolha uma opção:")
        print("1. Cadastrar")
        print("2. Entrar")
        print("3. Sair")
        opcao = input("Digite a opção desejada: ")

        if opcao == "1":
            nome = input("Digite o seu nome: ").strip()
            if nome in usuarios:
                print("Usuário já cadastrado.")
                continue
            idade = int(input("Digite a sua idade: "))
            if idade < 18:
                print("Você deve ser maior de idade para jogar.")
                continue
            saldo = float(input("Digite o seu saldo inicial: R$ "))
            senha = input("Digite a sua senha: ")
            usuarios[nome] = UsuarioDoCassino(nome, idade, saldo, senha)
            print(f"Usuário {nome} cadastrado com sucesso!")
        elif opcao == "2":
            nome = input("Digite o nome do usuário: ").strip()
            senha = input("Digite a senha: ")
            usuario = usuarios.get(nome)
            if usuario and usuario.verificar_senha(senha):
                print(f"Bem-vindo ao cassino, {usuario.nome}!")
                while True:
                    print("\nEscolha uma opção:")
                    print("1. Jogar")
                    print("2. Depositar")
                    print("3. Consultar saldo")
                    print("4. Sair")
                    escolha = input("Digite a opção desejada: ")

                    if escolha == "1":
                        print("\nEscolha um jogo:")
                        print("1. Blackjack")
                        print("2. Roleta")
                        print("3. Poker")
                        jogo = input("Digite o número do jogo desejado: ")
                        if jogo == "1":
                            blackjack(usuario)
                        elif jogo == "2":
                            roulette(usuario)
                        elif jogo == "3":
                            poker(usuario)
                        else:
                            print("Jogo inválido.")
                    elif escolha == "2":
                        valor = float(input("Digite o valor para depósito: R$ "))
                        usuario.depositar(valor)
                    elif escolha == "3":
                        print(f"Saldo atual: R$ {usuario.saldo:.2f}")
                    elif escolha == "4":
                        print("Saindo da conta.")
                        break
                    else:
                        print("Opção inválida.")
            else:
                print("Usuário ou senha incorretos.")

        elif opcao == "3":
            print("Obrigado por visitar o cassino. Até logo!")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()
