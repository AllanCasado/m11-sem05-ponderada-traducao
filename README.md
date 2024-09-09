# Respostas às perguntas da seção 9.5.7 

#### Tente valores diferentes do argumento num_examples na função load_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?

Alterar o valor do parâmetro num_examples na função load_data_nmt afeta diretamente o tamanho dos vocabulários, pois quanto mais exemplos são usados, mais palavras diferentes são observadas pelo modelo. Ao utilizar um número pequeno de exemplos, o vocabulário é limitado, contendo poucas palavras únicas, enquanto um número maior de exemplos aumenta o vocabulário, uma vez que mais palavras e expressões novas são incluídas. 

De acordo com os experimentos vistos na imagem abaixo, o vocabulário francês tende a crescer mais rapidamente que o inglês devido à maior diversidade gramatical e lexical nas traduções francesas. Por exemplo, com 100 exemplos, os vocabulários em ambos os idiomas têm cerca de 40 palavras, mas com 10.000 exemplos, o vocabulário de inglês cresce para 1.505 palavras e o de francês para 2.252 palavras.

![image](https://github.com/user-attachments/assets/c999af87-d12d-406f-b757-12d60a6609c7)

#### O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?

A tokenização em nível de palavra não é uma boa ideia para idiomas como chinês e japonês, pois esses idiomas não possuem delimitadores claros de palavras, como espaços, o que dificulta a segmentação de maneira programática das frases. Em vez disso, técnicas mais adequadas para esses casos incluem a tokenização em nível de caractere ou a segmentação baseada em subpalavras, como o método Byte Pair Encoding (BPE), que permite capturar unidades menores, como radicais ou caracteres individuais, garantindo um melhor tratamento desses idiomas, sem a necessidade de definir explicitamente os limites entre as palavras.
