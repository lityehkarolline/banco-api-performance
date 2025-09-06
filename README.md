# Tests de  Performance da API di Banco com K6

Este repositório contém testes de **performance** escritos em **JavaScript** utilizando a ferramenta [K6](https://k6.io/).  
O objetivo é validar o desempenho da aplicação [Banco API](https://github.com/juliodelimas/banco-api) sob diferentes cenários de carga.


## 📝 Introdução
Os testes de performance permitem avaliar a estabilidade, escalabilidade e capacidade de resposta da API em situações de uso real, simulando múltiplos usuários simultâneos.  
Este projeto foi criado com foco em:
- Simular cargas realistas de usuários;
- Monitorar métricas de tempo de resposta, throughput e taxa de erros;
- Garantir que a API suporte o volume esperado de requisições.

---

## 🛠️ Tecnologias utilizadas
- JavaScript (ES6)
- [K6](https://k6.io/) → ferramenta de testes de carga e performance
- [GJSON] Para extração de dados em resposta JSON,
- Variveis de ambiente para configuração dinamica Ex: BASE_URL

---

## 📂 Estrutura do repositório

```bash
banco-api-performance/
├── fixtures
├── helpers					     # Funções utilitarias reutilizaveis para a interação com a API
├── tests/
│   ├── login.test.js            # Cenário de teste de login
│   ├── transferencias.test.js   # Cenário de teste de transferências
│   ├── Configs                  # Arquivos de configuração de variáveis de ambiente
│   └── utils                    # Funções utilitarias reutilizaveis
│ 
├── package.json                 # Dependências e scripts do projeto
└── README.md                    # Documentação do projeto
```

### Objetivo de cada grupo de arquivos
- **tests/** → contém os arquivos de teste K6 para cada funcionalidade da API.
- **package.json** → armazena as dependências e metadados do projeto.
- **README.md** → documentação com instruções de instalação e execução.

---

## ⚙️ Instalação e execução do projeto

### 1. Clonar o repositório
```bash
git clone https://github.com/lityehkarolline/banco-api-performance.git
cd banco-api-performance
```

### 2. Instalar o K6
- [Guia de instalação oficial](https://k6.io/docs/get-started/installation/)

### 3. Configurar variável de ambiente
Antes de rodar os testes, configure a variável `BASE_URL` com a URL da API que deseja testar:
Altere o arquivo 'config.local.json'
```
{
 "baseUrl": "http://localhost:3000"
 }
```

### 4. Executar um teste
Exemplo: rodando o teste de login
```bash
k6 run tests/login.test.js
```

---

## 📊 Relatório em tempo real

Para acompanhar o relatório em tempo real e exportar em HTML:

```bash
K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run tests/login.test.js
```

Isso abrirá um **dashboard web** local e, ao final da execução, exportará os resultados para o arquivo `html-report.html`.

---

🔗 Repositório: [Banco API Performance](https://github.com/lityehkarolline/banco-api-performance)
