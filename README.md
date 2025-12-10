# Projeto de Criptoanálise - Decifragem sem Chave 🔐

Projeto de criptoanálise em Python cujo objetivo é recuperar uma mensagem original **sem conhecimento prévio da chave**, utilizando técnicas clássicas de criptografia, análise de frequência e otimização por *hill-climbing*.

A mensagem foi inicialmente fornecida em código binário, convertida para caracteres e análisadacom base em estatísticasde quadgrams do idioma inglês.

> **Status:** Projeto em expansão.
> 
> O trabalho original foi desenvolvido como estudo da disciplina de Arquitetura de Computadores.
<br>

## 🔧 Futuras Melhorias
- Implementar criptografia e decriptografia tanto para Cifra de César quanto para Cifra de Substituição Monoalfabética.
- Expandir o suporte atual (somente letras maiúsculas e sem pontuação) para:
  - letras minúsculas
  - pontuação
  - textos mais diversos
- Adicionar rotinas completas de:
  - Binário ↔ Char ↔ Texto Original
  - Char ↔ Texto Original
<br>

## 📘 Objetivos do Projeto
- Decodificar uma mensagem inicialmente fornecida em binário.
- Aplicar e testar cifras clássicas:
  - Cifra de César
  - Cifra de Substituição Monoalfabética
- Gerar uma chave inicial otimizada a partir da análise de frequência.
- Avaliar textos por score de quadgrams.
- Aplicar Hill-Climbing estocástico para otimizar a chave e aproximar-se do texto real.
<br>

## 🧠 Metodologia
### 1. Conversão da Mensagem
A mensagem cifrada foi inicialmente fornecida como sequência binária. Foi necessário convertê-la para ASCII/char e fazer um processamento prévio às análises.
### 2. Recursos de apoio utilizados
- Lista de quadgrams em inglês e seus respectivos scores.
- Função auxiliar para cálculo do score de um texto com base nos quadgrams.
- Quanto maior o score (menos negativo), mais provável é a proximidade do texto com o idioma real.
### 3. Aplicação da Cifra de César
Foram testadas as 26 rotações possíveis do alfabeto. Nenhuma forneceu resultado satisfatório, indicando que o método utilizado para cifragem não foi por rotação.
### 4. Aplicação da Cifra de Substituição Monoalfabética
Foi construída uma chave inicial baseada na frequência das letras observada no texto cifrado e na frequência típica do inglês. Essa chave serviu como ponto de partida para o método de otimização.
### 5. Otimização por Hill-Climbing Estocástico
Duas letras da chave são trocadas aleatoriamente e o novo texto é avaliado pelo score de quadgrams. Se o score melhora, a troca é mantida.
- A chave inicial baseada em frequências ajudou:
 - a acelerar a convergência,
 - a evitar máximos locais frequentes do hill-climbing tradicional. 
### 6. Avaliação Final
Cada texto é pontuado com base na probabilidade de seus quadgrams ocorrerem no inglês. As sequências comuns recebem pontuações maiores, enquanto combinações improváveis recebem pontuações menores.

<br>

## 🚀 Resultados (Versão Atual)
1. O projeto pode ser visualizado no arquivo Projeto_de_Criptoanálise.ipynb, disponível na raiz deste repositório.
2. Como o projeto ainda está em desenvolvimento, o repositório será futuramente reorganizado para incluir novas funcionalidades e permitir testes com textos variados.
3. O notebook disponibilizado corresponde ao estudo realizado na disciplina Arquitetura de Computadores, refletindo a implementação inicial do processo de criptoanálise.
> 🔎 *Os resultados apresentados aqui são apenas referentes à versão atual do notebook, que ainda será expandida e refinada.*

<br>

## Créditos
Este projeto foi desenvolvido como parte da disciplina Arquitetura de Computadores,
com base em material fornecido pelo professor e referências clássicas de criptoanálise.
  

