# 3D_Unet_com_Perda_Personalizada
Certificado de Registro de Programa de Computador - Processo Nº: BR512024005262-3

## Resumo
A evolução das técnicas de Imagem de Ressonância Magnética (IRM) desempenha um papel crucial na medicina diagnóstica, impulsionando avanços significativos. Neste estudo, busca-se explorar a eficácia e o desempenho de um modelo 3D U-Net, treinado com conjuntos de imagens de IRM com a utilização de uma perda personalizada. O objetivo é detectar tumores cerebrais com um melhor desempenho, gerar previsões e avaliar seus resultados. As imagens utilizadas foram obtidas no formato NIFTI da competição BraTS2020, consistindo em 369 conjuntos de imagens, cada um contendo 5 imagens, essenciais para o treinamento do modelo.

Para alcançar os objetivos propostos, foram treinados dois modelos distintos: um utilizando a Perda Entropia Cruzada Categórica e outro utilizando uma perda combinada de Perda Entropia Cruzada Categórica e Perda Suave Dice. O melhor treinamento de cada modelo foi selecionado com base na avaliação das métricas de desempenho, incluindo precisão, sensibilidade, especificidade, índice de Jaccard, entre outras. Em seguida, os modelos otimizados foram utilizados para gerar previsões, que foram comparadas com as máscaras reais dos tumores para avaliar sua correspondência.

A análise comparativa das métricas de desempenho dos dois modelos permitiu determinar qual obteve melhor desempenho na tarefa de detecção de tumores cerebrais. Os resultados revelaram que a perda combinada proposta, que integra a Perda Entropia Cruzada Categórica e a Perda Suave Dice, alcançou melhores resultados em comparação com a utilizada na implementação padrão do modelo 3D U-Net. Essa descoberta destaca a importância das pesquisas nessa área para também explorar abordagens personalizadas de treinamento para modelos de aprendizado profundo. Visando, assim, melhorar sua eficácia em tarefas específicas, como a detecção de tumores cerebrais em imagens médicas de ressonância magnética.

## Arquitetura do Modelo 3D Unet
![3DUNET](https://github.com/user-attachments/assets/0a490b04-e016-47e4-bbbf-5f67624b9429)

Fonte: Adaptado de RONNEBERGER, et al. (2015)



## Tipos de imagens
![image](https://github.com/user-attachments/assets/fa197889-5b39-4ebe-b01d-49f71fa4cdcd)


## Treinamento utilizando diferentes métricas de perda

### Perda Entropia Cruzada Categórica (ECC)
Essa função de perda não é criada manualmente, dado que o modelo de arquitetura 3D
U-Net é comumente encontrado em bibliotecas populares de Python, ela é encapsulada
dentro do framework TensorFlow.

### Perda Entropia Cruzada Categórica combinada com a Perda Suave Dice (ECC + SDL)
Durante o treinamento do modelo, uma etapa crucial desta pesquisa envolve a utilização de uma perda personalizada, a qual combina a Entropia Cruzada Categórica (ECC) com a Perda Suave Dice (SDL). Essa combinação é fundamental para a proposta desta pesquisa, avaliando a discrepância entre as previsões do modelo e os rótulos
verdadeiros associados aos dados de treinamento, visto que a ECC é comumente utilizada
para tarefas de classificação multiclasse, enquanto a SDL é conhecida por sua capacidade
de lidar com a sobreposição de classes e produzir segmentações suaves e bem definidas. A
análise do impacto da utilização dessa perda personalizada no treinamento de um modelo
baseado na arquitetura 3D U-Net para a detecção de tumores cerebrais em imagens de
ressonância magnética é realizada por meio da comparação das métricas de desempenho dos modelos.

## A Perda Personalizada
![algoritm](https://github.com/user-attachments/assets/dc797b6c-6579-4209-b69f-5cfb21101f56)

## Critérios para Avaliação de Resultados
A avaliação de cada treinamento realizado para a escolha do melhor treinado foi levando em consideração todas essas métricas.

![image](https://github.com/user-attachments/assets/12253aa5-e6a5-4734-bc0e-1b739c97e147)


## Resultados

Previsões do modelo ECC

![image](https://github.com/user-attachments/assets/dbb1a4aa-2264-4581-9247-9dea90ca5be0)

Previsões do modelo ECC + SDL

![image](https://github.com/user-attachments/assets/ae09d9fb-4a99-426a-ab8a-6130796db5b1)



Ao final as previsões e comparações entre as imagens de cada modelo de perda

![image](https://github.com/user-attachments/assets/6ff2edb3-8517-4756-a201-7536debb8950)



Resumo dos resultados obtidos do melhor treinamento da cada modelo de perda (ECC e ECC + SDL)

![tabelaresuldados](https://github.com/user-attachments/assets/7645edef-e56b-43ab-97ed-6e3478e99fd1)







