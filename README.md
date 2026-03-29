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
## Prints da Execução:
### Dados da Telemetria primeira parte do código:
<img width="774" height="717" alt="dadosTelemetria" src="https://github.com/user-attachments/assets/7424505d-d054-4c5f-9f3a-8ee651418efd" />

### Dados da Telemetria segunda parte do código:
<img width="805" height="530" alt="dadosTelemetria2" src="https://github.com/user-attachments/assets/00bcab77-b0e7-428a-a9d4-fadc6d21c6b0" />

### Resultado Código da Telemetria:
<img width="589" height="704" alt="resultadoCodigoDaTelemetria" src="https://github.com/user-attachments/assets/06f5430a-a67b-45c9-b815-3749f99524b9" />

### Faixa de Segurança:
<img width="674" height="328" alt="faixaDeSeguranca" src="https://github.com/user-attachments/assets/bfd0276f-2f43-48e4-9336-13667c9a998c" />

### Aplicação da Faixa de Segurança:
<img width="1077" height="476" alt="faixaDeSegurançaAplicacao" src="https://github.com/user-attachments/assets/9d9fbe70-6699-484d-b510-47c0698ff67e" />

### Resultado Final do Código Aplicando todas as regras pré-definidas:
<img width="643" height="540" alt="resultadoCodigoFinal" src="https://github.com/user-attachments/assets/01124161-1711-45d3-be69-32718dbf014f" />


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


