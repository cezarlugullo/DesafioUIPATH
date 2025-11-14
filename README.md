# DesafioUIPATH

## 📋 Sobre o Projeto

Este repositório contém o Desafio UiPath - um projeto desenvolvido para demonstrar habilidades em automação de processos robóticos (RPA) utilizando a plataforma UiPath.

O desafio consiste em construir **duas automações** (projetos) diferentes que realizam o mesmo processo: **cadastro de oportunidades para o time de Vendas!**

## 🎯 Objetivo

Construir duas automações que trabalham em conjunto:

**AUTOMAÇÃO 1 - Extração de Dados**
- Extrair todas as informações da tabela do site [Report: Opportunities](https://www.rpasamples.com/opportunities)
- Enviar os dados extraídos para uma fila no UiPath Orchestrator

**AUTOMAÇÃO 2 - Cadastro no Sistema**
- Recuperar as informações da fila do Orchestrator
- Cadastrar as oportunidades no [Sistema Forms](https://forms.gle/GiWH5pFWrh5VVpAQ7)
- **Filtrar**: Cadastrar apenas os itens com origem nos **USA e Germany**
- Enviar um e-mail ao final indicando a conclusão do processo

## 🚀 Tecnologias Utilizadas

- **UiPath Studio**: Plataforma principal para desenvolvimento de automações
- **UiPath Robot**: Para execução dos processos automatizados
- **UiPath Orchestrator**: Para gerenciamento de filas e orquestração dos processos
- **Site RPA Samples**: [Report: Opportunities](https://www.rpasamples.com/opportunities) - Fonte de dados
- **Google Forms**: [Sistema Forms](https://forms.gle/GiWH5pFWrh5VVpAQ7) - Sistema de cadastro

## 📁 Estrutura do Projeto

```
DesafioUIPATH/
├── README.md                    # Documentação do projeto
├── Automacao1_Extracao/         # Projeto de extração de dados
│   └── Main.xaml                # Fluxo principal da automação 1
└── Automacao2_Cadastro/         # Projeto de cadastro no sistema
    └── Main.xaml                # Fluxo principal da automação 2
```

## 🔄 Diagrama do Fluxo

```
┌─────────────────────────┐
│   AUTOMAÇÃO 1           │
│                         │
│  Report: Opportunities  │
│  ↓                      │
│  Download das Info      │
│  ↓                      │
│  Envio para a Fila      │
└───────────┬─────────────┘
            │
            ↓
┌─────────────────────────┐
│  UIPATH ORCHESTRATOR    │
│                         │
│  Queue (Fila)           │
│  Informações dos itens  │
└───────────┬─────────────┘
            │
            ↓
┌─────────────────────────┐
│   AUTOMAÇÃO 2           │
│                         │
│  Pega da Fila           │
│  ↓                      │
│  Filtra (USA/Germany)   │
│  ↓                      │
│  Preenche Sistema Forms │
│  ↓                      │
│  Envia E-mail           │
└─────────────────────────┘
```

## 💻 Pré-requisitos

Antes de começar, você precisará:

- [UiPath Studio](https://www.uipath.com/product/studio) (versão Community ou superior)
- Conta gratuita no [UiPath Orchestrator](https://cloud.uipath.com/) (ou conta existente)
- Sistema Operacional: Windows 10/11
- .NET Framework 4.6.1 ou superior
- Navegador web (Chrome, Edge ou Firefox)
- Acesso à internet para acessar os sites externos

## 🔧 Instalação

1. Clone este repositório:
```bash
git clone https://github.com/cezarlugullo/DesafioUIPATH.git
```

2. Configure o UiPath Orchestrator:
   - Acesse [UiPath Cloud](https://cloud.uipath.com/)
   - Crie uma conta gratuita ou faça login
   - Crie uma nova fila (Queue) para armazenar as oportunidades
   - Anote as credenciais de acesso

3. Abra os projetos no UiPath Studio:
   - Inicie o UiPath Studio
   - Abra a **Automação 1** (Extração):
     - Selecione "Open" (Abrir)
     - Navegue até a pasta `Automacao1_Extracao`
     - Abra o arquivo `project.json` ou `Main.xaml`
   - Abra a **Automação 2** (Cadastro):
     - Selecione "Open" (Abrir)
     - Navegue até a pasta `Automacao2_Cadastro`
     - Abra o arquivo `project.json` ou `Main.xaml`

4. Configure as credenciais:
   - Atualize as configurações de conexão com o Orchestrator em ambos os projetos
   - Configure o nome da fila criada

## ▶️ Como Executar

### Executar Automação 1 (Extração de Dados)

1. Abra o projeto `Automacao1_Extracao` no UiPath Studio
2. Verifique as dependências e instale os pacotes necessários
3. Execute o fluxo principal através do botão "Run" (F5)
4. A automação irá:
   - Acessar o site [Report: Opportunities](https://www.rpasamples.com/opportunities)
   - Extrair todas as informações da tabela
   - Enviar os dados para a fila do Orchestrator
5. Acompanhe a execução através dos logs

### Executar Automação 2 (Cadastro no Sistema)

1. Certifique-se de que a Automação 1 foi executada com sucesso
2. Abra o projeto `Automacao2_Cadastro` no UiPath Studio
3. Execute o fluxo principal através do botão "Run" (F5)
4. A automação irá:
   - Recuperar os itens da fila do Orchestrator
   - Filtrar apenas oportunidades de **USA** e **Germany**
   - Cadastrar cada item no [Sistema Forms](https://forms.gle/GiWH5pFWrh5VVpAQ7)
   - Enviar um e-mail ao final confirmando a conclusão
5. Verifique o e-mail de confirmação

## 📝 Funcionalidades

### Automação 1 - Extração de Dados
- ✅ Acesso automatizado ao site Report: Opportunities
- ✅ Extração de dados da tabela de oportunidades
- ✅ Validação dos dados extraídos
- ✅ Envio dos dados para fila do UiPath Orchestrator
- ✅ Tratamento de erros e logs detalhados

### Automação 2 - Cadastro no Sistema
- ✅ Recuperação de itens da fila do Orchestrator
- ✅ Filtragem de oportunidades por origem (USA e Germany)
- ✅ Preenchimento automatizado do Sistema Forms
- ✅ Validação de cadastros realizados
- ✅ Envio de e-mail de confirmação ao final do processo
- ✅ Tratamento de erros e logs detalhados

## 🔗 Referências

- **Site de Origem dos Dados**: [Report: Opportunities](https://www.rpasamples.com/opportunities)
- **Sistema de Cadastro**: [Google Forms](https://forms.gle/GiWH5pFWrh5VVpAQ7)
- **UiPath Orchestrator**: [UiPath Cloud](https://cloud.uipath.com/)
- **UiPath Studio**: [Download](https://www.uipath.com/product/studio)

## 🧪 Testes

Para executar os testes:
1. Abra a seção de testes no UiPath Studio
2. Execute os casos de teste disponíveis
3. Verifique os resultados no painel de testes

## 📄 Licença

Este projeto está sob licença. Consulte o arquivo LICENSE para mais detalhes.

## 👤 Autor

**Cezar Lugullo**

- GitHub: [@cezarlugullo](https://github.com/cezarlugullo)

## 🤝 Contribuindo

Contribuições, issues e solicitações de recursos são bem-vindas!

## 📞 Suporte

Se você tiver alguma dúvida ou problema, sinta-se à vontade para abrir uma issue no repositório.

---

⭐️ Se este projeto foi útil para você, considere dar uma estrela!
