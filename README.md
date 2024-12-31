
# Calculadora Aritmética Vue.js

Este projeto é uma calculadora aritmética simples implementada usando Vue.js 3. A calculadora permite que os usuários realizem operações básicas de adição, subtração, multiplicação e divisão.

## Estrutura do Projeto

```
calculadora-aritmetica/
│
├── src/
│   ├── components/
│   │   ├── NumberInput.vue
│   │   ├── OperationSelect.vue
│   │   └── ResultDisplay.vue
│   │
│   ├── App.vue
│   └── main.js
│
├── public/
│   └── index.html
│
├── package.json
└── README.md
```

## Componentes

### 1. App.vue (Componente Principal)
Este é o componente principal que integra todos os outros componentes. Ele gerencia o estado da calculadora e realiza os cálculos com base nos inputs do usuário.

### 2. NumberInput.vue
Este componente é usado para entrada de números. Ele é reutilizado para ambos os operandos da calculadora.

### 3. OperationSelect.vue
Este componente permite ao usuário selecionar a operação aritmética desejada (adição, subtração, multiplicação ou divisão).

### 4. ResultDisplay.vue
Este componente exibe o resultado da operação aritmética.

## Como Funciona

1. O usuário insere dois números usando os componentes `NumberInput`.
2. O usuário seleciona uma operação usando o componente `OperationSelect`.
3. O componente principal `App.vue` observa essas mudanças e recalcula o resultado automaticamente.
4. O resultado é exibido no componente `ResultDisplay`.

A calculadora utiliza a reatividade do Vue.js para atualizar o resultado em tempo real, sem a necessidade de um botão de cálculo.

## Funcionalidades

- Realiza operações de adição, subtração, multiplicação e divisão.
- Atualiza o resultado em tempo real conforme o usuário altera os números ou a operação.
- Possui um design responsivo com tema escuro.
- Trata o caso de divisão por zero, exibindo uma mensagem de erro apropriada.

## Como Executar o Projeto

1. Certifique-se de ter o Node.js instalado em sua máquina.  
2. Clone este repositório:  
   ```bash
   git clone https://github.com/seu-usuario/calculadora-aritmetica.git
   ```  
3. Navegue até o diretório do projeto:  
   ```bash
   cd calculadora-aritmetica
   ```  
4. Instale as dependências:  
   ```bash
   npm install
   ```  
5. Execute o projeto em modo de desenvolvimento:  
   ```bash
   npm run dev
   ```  
6. Abra seu navegador e acesse `http://localhost:5173` (ou a porta indicada no terminal).

## Personalização

Você pode personalizar o tema da calculadora ajustando as cores no arquivo `App.vue` e nos componentes individuais.

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir *issues* ou enviar *pull requests* com melhorias.

## Licença

Este projeto está licenciado sob a [MIT License](https://opensource.org/licenses/MIT).
