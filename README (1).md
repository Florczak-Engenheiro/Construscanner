# �️ Monitor Inteligente de Canteiro de Obras

Sistema inteligente de **fiscalização, monitoramento e análise de risco** para canteiros de construção civil, desenvolvido com **Inteligência Artificial e IoT**.

## 🎯 Funcionalidades Principais

### 📊 Monitoramento em Tempo Real
- Coleta contínua de dados de múltiplos sensores
- Visualização instantânea de métricas
- Dashboard interativo com alertas

### 🤖 Análise de Risco com IA
- **Análise Multidimensional**: Equipamento, Ambiente e Pessoal
- **Cálculo Dinâmico**: Algoritmo ponderado que ajusta em tempo real
- **Alertas Inteligentes**: Sistema automático de avisos críticos e alertas
- **Histórico Completo**: Rastreamento de toda operação

### 📈 Relatórios e Estatísticas
- Histórico detalhado de operação
- Gráficos temporais de evolução de riscos
- Relatórios consolidados de segurança

## 🚀 Tecnologias Utilizadas

- **Streamlit**: Interface web moderna e responsiva
- **Plotly**: Visualizações gráficas avançadas
- **Pandas**: Processamento de dados
- **Python 3.8+**: Backend robusto

## 📋 Métricas Monitoradas

### 🏭 Equipamento (35% do risco)
- Temperatura (°C)
- Vibração (mm/s)
- Horas de operação contínua

### 🌍 Ambiente (30% do risco)
- Umidade relativa (%)
- Ruído (dB)
- Temperatura ambiental (°C)

### 👥 Pessoal (35% do risco)
- Quantidade de operários
- Uso de EPI (Equipamento de Proteção Individual)
- Proteção auditiva

## 🔴 Níveis de Risco

| Nível | Faixa | Status | Ação |
|-------|-------|--------|------|
| 🟢 SEGURO | 0-40% | Operação normal | Monitoramento de rotina |
| 🟠 ALERTA | 40-70% | Risco moderado | Aumentar monitoramento |
| 🔴 CRÍTICO | >70% | Alto risco | Parada e investigação |

## 🏃 Como Executar Localmente

### 1. Pré-requisitos
- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Git

### 2. Clonar o Repositório
```bash
git clone https://github.com/Florczak-Engenheiro/blank-app.git
cd blank-app
```

### 3. Criar Ambiente Virtual (Recomendado)
```bash
python -m venv venv

# Linux/Mac
source venv/bin/activate

# Windows
venv\Scripts\activate
```

### 4. Instalar Dependências
```bash
pip install -r requirements.txt
```

### 5. Executar a Aplicação
```bash
streamlit run streamlit_app.py
```

A aplicação abrirá em `http://localhost:8501`

## 🌐 Deploy Online (Streamlit Cloud)

### Opção 1: Deploy Automático

1. **Fazer Login no Streamlit Cloud**
   - Acesse https://share.streamlit.io
   - Login com GitHub

2. **Deploy da Aplicação**
   - Clique em "New app"
   - Conecte seu repositório GitHub
   - Selecione a branch `main`
   - Defina o arquivo principal: `streamlit_app.py`
   - Clique em "Deploy"

### Opção 2: Deploy via CLI

```bash
pip install streamlit

streamlit-cli deploy --app-name monitor-canteiro \
  --email seu-email@exemplo.com \
  --password sua-senha
```

## 📊 Estrutura do Projeto

```
blank-app/
├── streamlit_app.py        # Interface web principal
├── monitor_canteiro.py     # Módulo de lógica (IA e sensores)
├── requirements.txt        # Dependências Python
├── README.md              # Este arquivo
├── LICENSE                # Licença do projeto
└── .streamlit/
    └── config.toml        # Configuração do Streamlit (opcional)
```

## 🔧 Componentes Principais

### `monitor_canteiro.py`

#### `DadosSensor`
Dataclass que armazena leitura de todos os sensores

#### `AnalisadorRisco`
Classe que implementa a IA para análise multidimensional:
- `calcular_risco_equipamento()`: Analisa dados do equipment
- `calcular_risco_ambiente()`: Analisa condições ambientais
- `calcular_risco_pessoal()`: Analisa segurança pessoal
- `calcular_risco_geral()`: Consolida análise final

#### `SensorSimulador`
Simula dados realistas de sensores com inércia temporal

#### `SistemaMonitoramento`
Orquestra o funcionamento completo do sistema

### `streamlit_app.py`

Interface com 4 modos:
1. **Monitoramento**: Visualização em tempo real
2. **Histórico**: Gráficos e análise de tendências
3. **Relatório**: Resumo consolidado
4. **Informações**: Documentação do sistema

## 🎮 Como Usar

### Modo Monitoramento
1. Os dados são coletados automaticamente a cada ciclo
2. Visualize o nível de risco geral (0-100%)
3. Observe os alertas relacionados
4. Use a barra lateral para ajustar velocidade de coleta

### Modo Histórico
1. Visualize gráficos de evolução de cada métrica
2. Análise de correlação entre variáveis
3. Identifique padrões e tendências

### Modo Relatório
1. Visualize estatísticas consolidadas
2. Análise sobre o nível geral de segurança
3. Recomendações baseadas em dados

## 🤝 Melhorias Implementadas vs. Código Original

### ✅ Adicionado
- ✨ Análise de risco multidimensional com IA
- 📊 Cálculo da distribuição ponderada de riscos
- 🚨 Sistema inteligente de alertas e avisos
- 📈 Histórico de dados com estatísticas
- 🎨 Interface Streamlit profissional e responsiva
- 📉 Gráficos interativos com Plotly
- 📋 Relatórios consolidados
- 🏭 Mais sensores (vibração, umidade, ruído, etc)
- 👥 Monitoramento de segurança pessoal (EPI)
- 🔄 Simulação realista com inércia de dados

### 🔧 Refatorado
- Estrutura orientada a objetos (Classes)
- Separação clara de responsabilidades
- Código mais testável e manutenível
- Documentação completa

### ⚡ Melhorias de Performance
- Limite de histórico (últimas 1000 medições)
- Cálculos otimizados
- Renderização eficiente

## 📚 API do Módulo

```python
from monitor_canteiro import SistemaMonitoramento

# Inicializar
sistema = SistemaMonitoramento()

# Coletar e processar em um ciclo
resultado = sistema.coletar_e_processar()

# Acessar dados
dados = resultado["dados"]
analise_risco = resultado["analise_risco"]

# Gerar relatório
relatorio = sistema.obter_relatorio()
```

## 🔐 Segurança

- ✅ Sem armazenamento de dados sensíveis
- ✅ Sem conexão externa de sensores (simulação)
- ✅ Ideário para prototipagem
- ⚠️ Para produção, integre com real IoT devices

## 📝 Licença

Este projeto está sob a licença [especificar licença]

## 👨‍💼 Autor

**Desenvolvido como projeto de Engenharia Civil com IA**

---

## 🆘 Suporte e Dúvidas

Para dúvidas ou sugestões, entre em contato ou abra uma issue no repositório.

## 🎓 Aprendizados

Este projeto demonstra:
- Sistema de monitoramento IoT completo
- Implementação de IA para análise de risco
- Desenvolvimento web com Streamlit
- Best practices em Python
- Deploy em nuvem (Cloud)
