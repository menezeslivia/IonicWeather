# 🌦️ Ionic Weather App
Aplicativo de previsão do tempo desenvolvido com Ionic + Angular

## 📋 Descrição do Projeto
Aplicativo móvel para monitoramento climático desenvolvido com Ionic, consumindo a API OpenWeatherMap.

## 🎯 Objetivo
Fornecer previsões meteorológicas em tempo real com interface responsiva e funcionalidades de personalização.

## 👥 Equipe (4-6 membros)
| Função               | Nome               | Responsabilidades                          |
|----------------------|--------------------|-------------------------------------------|
| Scrum Master         | Clara Heloisa             | Gerenciamento do projeto                  |
| Gerente Config       | Fernanda Gabrielli        | Repositório Git e padrões                 |
| Documentador 1       | Clara Heloisa             | Casos de uso e protótipos                 |
| Documentador 2       | Fernanda Buonafina        | Diagramas UML/ER                          |
| Desenvolvedor 1      | Livia Menezes        | Front-end e integração API                |
| Desenvolvedor 2      | Fernanda Buonafina           | Autenticação e banco de dados             |


## ✨ Funcionalidades
- Previsão do tempo em tempo real
- Busca por cidade
- Favoritar locais
- Previsão para os próximos dias
- Interface responsiva
- Gradiente animado

## 🛠 Tecnologias
- Ionic 7
- Angular 15
- OpenWeatherMap API
- Capacitor (para builds nativos)

## 🚀 Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/menezeslivia/IonicWeather.git
cd IonicWeather
```

2. Instale as dependências:
```bash
npm install
```

3. Execute localmente:
```bash
ionic serve
```

4. Para build Android/iOS:
```bash
ionic capacitor add android
ionic capacitor run android
```
## 🌦️ Documentação de Casos de Uso

Este documento apresenta os principais casos de uso do aplicativo **IonicWeather**, desenvolvido com Ionic + Angular. O app permite que usuários consultem informações climáticas em tempo real, salvem cidades favoritas e recebam alertas sobre mudanças climáticas.

---

### 📑 Sumário

- [UC001 - Realizar Login no Sistema](#uc001---realizar-login-no-sistema)
- [UC002 - Realizar Cadastro de Usuário](#uc002---realizar-cadastro-de-usuário)
- [UC003 - Buscar Cidade e Verificar Clima](#uc003---buscar-cidade-e-verificar-clima)
- [UC004 - Adicionar Cidade aos Favoritos](#uc004---adicionar-cidade-aos-favoritos)
- [UC005 - Consultar Clima da Localização Atual (GPS)](#uc005---consultar-clima-da-localização-atual-gps)
- [UC006 - Receber Notificações Climáticas](#uc006---receber-notificações-climáticas)

---

#### ✅ UC001 — Realizar Login no Sistema

- **Ator Principal:** Usuário  
- **Objetivo:** Permitir que o usuário entre no sistema utilizando credenciais válidas.  
- **Pré-condição:** O usuário deve possuir uma conta cadastrada.  
- **Pós-condição:** O usuário acessa as funcionalidades restritas (favoritos, histórico, notificações).  

##### 🔗 Fluxo Principal
1. O usuário abre o app.
2. Insere e-mail e senha na tela de login.
3. O sistema valida as credenciais.
4. Se válidas, o usuário é autenticado e acessa a tela inicial.

##### 🔀 Fluxo Alternativo
- **Esqueceu a senha:**  
  - O usuário clica em "Esqueci minha senha".  
  - O sistema solicita o e-mail e envia um link de redefinição.  

##### ⚠️ Tratamento de Exceções
- E-mail ou senha inválidos.
- Conta não existente.
- Problemas de conexão com o servidor.

---

#### ✅ UC002 — Realizar Cadastro de Usuário

- **Ator Principal:** Usuário  
- **Objetivo:** Permitir que novos usuários criem uma conta.  
- **Pré-condição:** Nenhuma.  
- **Pós-condição:** O usuário possui uma conta ativa no sistema.  

##### 🔗 Fluxo Principal
1. O usuário seleciona “Criar Conta”.
2. Preenche nome, e-mail e senha.
3. O sistema valida os dados.
4. Cria a conta.
5. Usuário é redirecionado para a tela inicial.

##### ⚠️ Tratamento de Exceções
- E-mail já cadastrado.
- Senha fraca (exibir aviso).
- Problemas na conexão.

---

#### ✅ UC003 — Buscar Cidade e Verificar Clima

- **Ator Principal:** Usuário  
- **Objetivo:** Permitir que o usuário consulte o clima de qualquer cidade.  
- **Pré-condição:** Usuário autenticado ou como visitante.  
- **Pós-condição:** Clima e previsão da cidade são exibidos.  

##### 🔗 Fluxo Principal
1. O usuário digita o nome da cidade.
2. O sistema consulta a API OpenWeatherMap.
3. Exibe dados atuais: temperatura, clima (chuva, sol, nublado), umidade e previsão.

##### ⚠️ Tratamento de Exceções
- Cidade não encontrada.
- API indisponível.
- Erro de conexão.

---

#### ✅ UC004 — Adicionar Cidade aos Favoritos

- **Ator Principal:** Usuário  
- **Objetivo:** Permitir que o usuário salve cidades favoritas para acesso rápido.  
- **Pré-condição:** Usuário autenticado.  
- **Pós-condição:** A cidade aparece na lista de favoritos do usuário.  

##### 🔗 Fluxo Principal
1. O usuário acessa uma cidade.
2. Clica no botão “Adicionar aos Favoritos”.
3. O sistema salva a cidade na base de dados do usuário (Firebase/local storage).

##### ⚠️ Tratamento de Exceções
- Falha no salvamento dos dados.
- Problema de conexão.

---

#### ✅ UC005 — Consultar Clima da Localização Atual (GPS)

- **Ator Principal:** Usuário  
- **Objetivo:** Permitir que o usuário consulte o clima da sua localização atual.  
- **Pré-condição:** Permissão de acesso ao GPS concedida.  
- **Pós-condição:** Exibe clima e previsão da localização atual do usuário.  

##### 🔗 Fluxo Principal
1. O usuário escolhe “Usar minha localização”.
2. O app solicita acesso ao GPS.
3. O sistema obtém latitude e longitude.
4. Consulta a API e exibe os dados.

##### ⚠️ Tratamento de Exceções
- Permissão de GPS negada.
- GPS indisponível.
- API indisponível.

---

#### ✅ UC006 — Receber Notificações Climáticas

- **Ator Principal:** Usuário  
- **Objetivo:** Alertar o usuário sobre mudanças climáticas severas.  
- **Pré-condição:** Usuário autenticado e com notificações ativas.  
- **Pós-condição:** O usuário recebe notificações push sobre alertas climáticos.  

##### 🔗 Fluxo Principal
1. O sistema verifica mudanças climáticas relevantes (ex.: tempestades, calor extremo).
2. Envia notificações push ao usuário.
3. O usuário acessa a notificação e verifica os detalhes no app.

##### ⚠️ Tratamento de Exceções
- Usuário sem permissão para notificações.
- Falha no envio das notificações.

## 🤝 Como Contribuir
1. Faça um fork do projeto
2. Crie sua branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas alterações (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 📝 Licença
Este projeto está sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes

---
