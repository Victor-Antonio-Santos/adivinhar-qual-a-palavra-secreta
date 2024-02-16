# adivinhar-qual-a-palavra-secreta
Você vai propor uma palavra secreta qualquer e vai dar a possibilidade para o usuário digitar apenas uma letra


import os

palavra_secreta = str(input('Digite uma palavra para alguém tentar adivinhar: '))
letras_acertadas = ''
numero_tentativas = 0

while True:

    
    letra_digitada = input('Digite uma letra: ')
    numero_tentativas += 1
    
    if letra_digitada == 'perfume':
        print('VOCÊ GANHOU!! PARABÉNS!')
        print('A palavra era', palavra_secreta)
        print('Tentativas:', numero_tentativas)
        break

    if len(letra_digitada) > 1:
        print('Digite apenas uma letra.')
        continue

    if letra_digitada in palavra_secreta:
        letras_acertadas += letra_digitada

    palavra_formada = ''
    for letra_secreta in palavra_secreta:
        if letra_secreta in letras_acertadas:
            palavra_formada += letra_secreta
        else:
            palavra_formada += '*'

    print('Palavra formada:', palavra_formada)

    if palavra_formada == palavra_secreta:
        os.system('clear')
        print('VOCÊ GANHOU!! PARABÉNS!')
        print('A palavra era', palavra_secreta)
        print('Tentativas:', numero_tentativas)
        letras_acertadas = ''
        numero_tentativas = 0
