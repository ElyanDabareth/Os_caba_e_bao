# Gêmeo Digital: Eficiência de Painéis Solares ☀️

**Disciplina:** Física Computacional I  
**Curso:** Engenharia Física - Universidade Federal de Goiás (UFG)  
**Autores:** João Paulo Messias e Carlos André  

## 📌 Sobre o Projeto
Este repositório contém o desenvolvimento de um programa de Física Computacional focado na modelagem de incidência solar e na análise de eficiência energética de painéis fotovoltaicos. 

O objetivo do projeto é duplo:
1. **Estabelecer um Modelo Ideal:** Utilizar equações astronômicas de geometria solar para calcular a irradiação solar em um plano inclinado específico na cidade de Goiânia, validando a física do sistema a partir de dados meteorológicos reais do INMET.
2. **Desenvolver um Gêmeo Digital:** Simular o funcionamento de um hardware de monitoramento, inserindo ruídos estocásticos (como simulação de sombreamento e acúmulo de poeira) para criar um algoritmo comparador capaz de detectar falhas de eficiência nas placas.

## 📂 Estrutura do Repositório

O trabalho foi dividido em fases de desenvolvimento para facilitar a manutenção e leitura do código:

* 📁 **`data/`**: Contém as bases de dados brutas utilizadas para validar o modelo (ex: planilhas históricas de irradiação do INMET).
* 📁 **`notebooks/`**: Ambientes interativos com o detalhamento da teoria física e os respectivos blocos de código em Python.
  * `Fase01_Geometria_Solar.ipynb` - Modelagem astronômica (Declinação Solar, Ângulo Horário, Ângulo de Incidência).
  * `Fase02_Modelo_Ideal.ipynb` - Integração com dados do INMET e cálculo do Fator K de correção para o plano inclinado.
  * `Fase03_Gemeo_Digital.ipynb` - (*Em desenvolvimento*) Inserção de ruídos e algoritmo comparador.
* 📁 **`docs/`**: Documentação acadêmica e o relatório final do projeto.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas Principais:** `numpy`, `pandas`, `matplotlib`
* **Ambiente de Desenvolvimento:** Google Colab / Jupyter Notebooks

## 📖 Referência Principal
A fundamentação matemática para a geometria solar foi baseada no trabalho:
> FRANCO, Guthierry Fernandes. *A rota do Sol e sua influência na produtividade de sistemas fotovoltaicos*. Trabalho de Conclusão de Curso (Graduação em Engenharia Elétrica) – Escola de Engenharia Elétrica, Mecânica e de Computação, UFG. Goiânia, 2021.
