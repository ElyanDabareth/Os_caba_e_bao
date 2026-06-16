# 📊 Base de Dados Meteorológicos (INMET)

Esta pasta é estritamente destinada ao armazenamento dos dados brutos utilizados para validar o modelo físico e alimentar o simulador do Gêmeo Digital.

## 📌 Origem dos Dados
Os dados históricos são extraídos das Estações Automáticas do **Instituto Nacional de Meteorologia (INMET)**.
* **Estação de Referência:** A002 (Goiânia - GO)
* **Localização:** Câmpus Samambaia (UFG) 
* **Latitude/Longitude:** -16.63° / -49.23°
* **Altitude:** 717 m

## 📖 Dicionário de Variáveis
As planilhas baixadas (`.csv`) contêm leituras horárias. O nosso software em Python (`pandas`) filtra as seguintes colunas essenciais para o cálculo de eficiência:

| Coluna Original (INMET) | Variável no Código | Unidade Física | Descrição |
| :--- | :--- | :--- | :--- |
| `Data/Hora (Local)` | `data_hora` | YYYY/MM/DD HH:MM | Marcação temporal da leitura. Utilizada para extrair o Dia Juliano ($n$) e a Hora Solar ($H_s$). |
| `Radiação (KJ/m2)` | `g_horizontal` | $Wh/m^2$ | Irradiação Global Horizontal ($G_{GH}$). **Nota:** O código converte este valor de $kJ/m^2$ para $Wh/m^2$ dividindo-o por 3,6. |
| `T (°C)` | `temp_ambiente` | $^\circ C$ | Temperatura de Bulbo Seco. Utilizada na termodinâmica para calcular a Temperatura da Célula ($T_{cell}$) e aplicar perdas por aquecimento. |

## ⚙️ Instruções para Atualização / Reprodução
Caso seja necessário simular novas datas ou baixar dados de outras regiões do país para testar a robustez do Gêmeo Digital:
1. Acesse o portal do INMET ou o sistema de monitoramento da SEMARH-GO.
2. Filtre por **Dados Horários** em **Estações Automáticas**.



3. Selecione o período desejado (recomenda-se baixar uma janela de 3 dias para garantir que não haja cortes devido ao fuso horário UTC).
4. Exporte o arquivo como `.csv` (separado por vírgulas, com separador decimal em ponto).
5. Salve o arquivo nesta pasta e atualize o caminho de leitura no script da `Fase02_Modelo_Ideal.ipynb`.
