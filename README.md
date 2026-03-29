# Aurora Singer 


##  Sobre o Projeto

Sistema desenvolvido em Python para analisar dados de telemetria de naves espaciais e decidir automaticamente se uma nave está **PRONTA PARA DECOLAR** ou se a **DECOLAGEM DEVE SER ABORTADA**, com base em faixas de segurança predefinidas.

---

##  Arquivos

```
projeto/
├── auroraSinger.ipynb       # Notebook principal
└── telemetria_decolagem.csv # Dataset com 500 naves
```

---

## Como o Sistema Funciona

**1. Análise da Telemetria**
Lê e interpreta os dados brutos de cada sensor, exibindo média de cada parâmetro monitorado junto com a quantidade de naves fora da faixa segura.

**2. Análise Energética**
Calcula se a carga disponível é suficiente para a decolagem considerando capacidade total, nível de energia atual, consumo estimado e perdas energéticas.

```
Carga disponível   = capacidade_total_kwh × (energia_pct / 100)
Energia necessária = consumo_decolagem_kwh × (1 + perdas_pct / 100)
```

**3. Status dos Módulos Críticos**
Classifica cada nave com base nos sensores em três categorias: `ok`, `alerta` ou `critico`.

**4. Decisão Final**
Aplica regras de faixa de segurança e define `PRONTO PARA DECOLAR` ou `DECOLAGEM ABORTADA` para cada nave.

---

## Parâmetros e Faixas de Segurança

| Parâmetro | Faixa Segura |
|-----------|-------------|
| Temperatura interna | 18°C a 27°C |
| Temperatura externa | -40°C a 80°C |
| Nível de energia | > 40% |
| Pressão dos tanques | 1.5 a 3.0 bar |
| Integridade estrutural | 1 (ok) |

---


## Instruções de Execução

### Pré-requisitos

- Python 3.x instalado
- Biblioteca `pandas` instalada

### 1. Instale a dependência

```bash
pip install pandas
```

### 2. Certifique-se que os arquivos estão na mesma pasta

```
pasta_do_projeto/
├── auroraSinger.ipynb
└── telemetria_decolagem.csv
```

### 3. Execute o notebook

**Via Jupyter Notebook / JupyterLab:**
```bash
jupyter notebook auroraSinger.ipynb
```

**Via Google Colab:**
- Faça upload do arquivo `auroraSinger.ipynb` no Google Colab
- Faça upload do arquivo `telemetria_decolagem.csv` na sessão


### 4. Resultado esperado

O notebook exibirá o relatório completo de telemetria, análise energética, status dos módulos e a decisão final de decolagem para cada uma das 500 naves.

