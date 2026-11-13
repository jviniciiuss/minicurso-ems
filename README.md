# Sistemas de Gerenciamento de Energia: estudo de caso

Notebook do **Minicurso: Sistemas de Gerenciamento de Energia: Definições, Estratégias e Aplicação** (Dia 2).

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jviniciiuss/minicurso-ems/blob/main/minicurso_ems.ipynb)

## A pergunta

Um consumidor industrial do Grupo A (subgrupo A4), atendido pela Energisa Paraíba em João Pessoa, quer reduzir a conta de energia.

> Vale a pena instalar uma usina fotovoltaica (UFV), um sistema de armazenamento em baterias (BESS) ou os dois? Em qual modalidade tarifária, azul ou verde?

## O que o notebook faz

1. **Premissas**: todos os números do estudo ficam em uma célula só.
2. **Consumo**: monta uma curva de carga horária sintética (perfil por tipo de dia, feriados, sazonalidade e ruído).
3. **Geração fotovoltaica**: calcula a geração a partir de dados horários de irradiância e temperatura da NASA POWER.
4. **Dimensionamento**: define a potência da UFV e a energia e potência do BESS.
5. **Cenários**: compara só rede (C1), rede + UFV (C2), rede + BESS (C3) e rede + UFV + BESS (C4).
6. **Faturamento**: calcula a fatura nas modalidades azul e verde, com demanda contratada, ultrapassagem e compensação de energia (SCEE).
7. **Estratégias de EMS**: controla a bateria por regras, com time shifting e peak shaving.
8. **Investimento**: calcula o custo evitado, o fluxo de caixa em 20 anos, o payback e o VPL.

No fim há exercícios: mude as premissas, rode de novo e compare.

## Como usar

**No Google Colab**: clique no botão acima e use *Ambiente de execução → Executar tudo*. Os dados climáticos são baixados deste repositório automaticamente.

**No computador**: com Python 3.10 ou mais recente, clone o repositório e instale as dependências.

```bash
git clone https://github.com/jviniciiuss/minicurso-ems.git
cd minicurso-ems
pip install numpy pandas matplotlib holidays jupyter
jupyter notebook minicurso_ems.ipynb
```

Rode as células em ordem, porque cada uma depende das anteriores.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| `minicurso_ems.ipynb` | O estudo de caso completo |
| `dados_nasa_power.csv` | Irradiância (`ALLSKY_SFC_SW_DWN`) e temperatura do ar (`T2M`) horárias de 2025 em João Pessoa, da [NASA POWER](https://power.larc.nasa.gov/) |

## Simplificações

O modelo é didático. Algumas simplificações estão anotadas no próprio notebook:
- a bateria não tem perdas;
- os créditos de energia não expiram;
- o ICMS incide sobre toda a demanda faturada;
- a curva de carga é sintética.

Os resultados ilustram o método e não substituem um estudo de viabilidade real.

## Ministrantes

José Vinícius Santos Freitas e Ruan Henrique Marques de Morais
