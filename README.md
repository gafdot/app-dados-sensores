### **Documentação do Projeto**

## Índice
1. **Descrição do Projeto**
2. **Instruções de Instalação e Configuração**
3. **Instruções de Uso**
4. **Arquitetura do Projeto**
5. **Documentação do Código**

---

## 1. Descrição do Projeto

Este é um aplicativo móvel React Native que permite aos usuários realizar login, registrar-se e visualizar dados de sensores em gráficos dinâmicos. A tela de gráficos exibe os dados coletados em tempo real, recebidos por WebSocket e HTTP, permitindo alternância entre tipos de gráficos e intervalos de tempo.

---

## 2. Instruções de Instalação e Configuração

### Pré-requisitos
- **Node.js**: Instale o Node.js para gerenciar dependências.
- **Expo CLI**: Recomendado para inicializar e testar o aplicativo em dispositivos móveis.
- **Servidor Backend**: O aplicativo precisa de um backend em Node.js rodando na porta 3000 com endpoints `/login`, `/register` e `/dados-sensores`.

### Instalação

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/gafdot/app-dados-sensores
   cd app-dados-sensores
   ```

2. **Instale as dependências**:
   ```bash
   npm install
   ```

3. **Inicie o aplicativo com Expo**:
   ```bash
   expo start
   ```

4. **Configuração do Servidor**:
   - Configure o servidor backend para receber dados de login, registro e sensores.
   - Certifique-se de que o backend tenha a URL `http://localhost:3000` ou atualize as URLs nos arquivos `GraphScreen.js`, `LoginScreen.js`, e `RegisterScreen.js` conforme necessário.

---

## 3. Instruções de Uso

1. **Login**: Execute o aplicativo, forneça as credenciais de login e pressione "Entrar". Em caso de sucesso, você será redirecionado para a tela de gráficos.
2. **Registro**: Caso não tenha uma conta, registre-se fornecendo um nome de usuário e senha.
3. **Visualização de Gráficos**: Após o login, visualize os dados dos sensores, escolha o tipo de gráfico (linha ou barra) e o intervalo de tempo para filtragem.

---

## 4. Arquitetura do Projeto

Este projeto é estruturado com quatro principais componentes de tela (arquivos `.js`) e organiza navegação entre eles. A navegação é gerenciada usando a biblioteca `@react-navigation`.

- **App.js**: Define a navegação e telas principais.
- **LoginScreen.js**: Gerencia o login e autenticação de usuário.
- **RegisterScreen.js**: Permite registro de novos usuários.
- **GraphScreen.js**: Visualiza dados de sensores em tempo real usando WebSocket e gráficos dinâmicos.

### Fluxo de Navegação
1. **App.js** carrega a primeira tela como `LoginScreen`.
2. Usuários autenticados são redirecionados para `GraphScreen`.
3. A tela `RegisterScreen` é acessada via `LoginScreen` e retorna ao login após o registro.
