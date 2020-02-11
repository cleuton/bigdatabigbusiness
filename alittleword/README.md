![](../bigdatabigbusiness.png)

# Bigdata, big business

Big data tutorials & samples!

[**Cleuton Sampaio**](https://github.com/cleuton)

[![](../banner_livros2.png)](https://www.lcm.com.br/site/#livros/busca?term=cleuton)

# Parte 1: A little word...

# Bigdata: O que não nos disseram...

Olá! Este é o primeiro artigo deste blog sobre a tecnologia de **Bigdata** e eu quero ser o mais franco possível com você: 

*Bigdata é uma solução em busca de um problema*

**Ahn... Como assim?**

Minha cara, meu caro, é isso mesmo! Bigdata é semelhante ao **Blockchain**: Ninguém sabe direito como e porquê usar, mas todos querem embarcar nessa "onda".

Deixe-me ser mais claro. As pessoas ainda não entenderam o valor da tecnologia de Bigdata e os **vendedores**, aproveitando a *hype*, querem te enfiar um monte de produtos e serviços pela "goela"... Será que você precisa realmente deles?

## 5 V

**Bigdata** é tipo de processamento e sumarização, executado sobre um grande e variado conjunto de dados, com o objetivo de entender um processo e detectar eventos instantaneamente. 

Diz-se que Bigdata pode ser caracterizado por cinco letras "V": 
- **Velocidade**: Dados são gerados a todo instante, e o Bigdata serve para analisá-los no momento em que são criados;
- **Volume**: Dados em grande volume, como mensagens de milhares de sensores remotos, ou milhões de "tweets" por exemplo; 
- **Variedade**: Mix de formatos estruturados e não estruturados. Tabelas de bancos de dados, arquivos textuais, sons, imagens etc;
- **Veracidade**: Os dados são confiáveis, sua qualidade é boa? Podemos confiar?
- **Valor**: Podemos extrair valor destes dados? Nos levam à conclusões relevantes?

## BI e Data Warehouse 

Precisamos contrastar Bigdata com BI, em especial Data warehouses. Em princípio, parecem ser a mesma coisa e acredite: Muita gente confunde isso e tenta fazer do "Hadoop" uma espécie de Data Warehouse. 

A diferença não é o volume de dados, mas a velocidade e variedade. Em um processo tradicional de BI, utilizamos Data Warehouses, nas quais os dados foram limpos e formatados para consultas analíticas, provavelmente utilizando modelagem dimensional. E também são dados de transações passadas, que nos permitirão verificarmos possibilidades de aumento de eficiência ou de redução de perdas. Em suma, coletamos, organizamos e analisamos os dados passados. 

Com Bigdata, os dados são oriundos de fontes heterogêneas e seu valor está associado ao seu "frescor", ou seja, quanto mais próximos do tempo real, maior seu valor. Quando pensamos em Bigdata, queremos analisar os fatos enquanto acontecem, possibilitando correções de rumo instantâneas. Daí a "Velocidade" e "Variedade" serem os conceitos mais importantes. 

Vou dar um exemplo melhor: 

- **BI**: Uma empresa aérea coleta os dados dos vôos durante o ano, para analisar possibilidades de promoções e reorganizações logísticas de carga;
- **Bigdata**: Uma empresa aérea coleta informações dos aviões durante o vôo, para analisar consumo de combustível nas rotas e reorientar os aviões.

Percebeu a diferença? É claro que os dados de consumo durante o vôo são importantes, mas, para o problema de reorientação do vôo (aumentar altitude, mudar ligeiramente a rota para diminuir a resistência do ar) é preciso que estes dados sejam em "tempo real".

## Data lake

Alguns vendem a ideia de que você deve criar grandes repositórios de dados, em formato bruto, chamados de "data lakes", como estratégia para implementação de Bigdata. Eles geralmente pregam que devemos utilizar o file system distribuído do Hadoop: HDFS para criar um gigantesco repositório de informações diversas para futura análise. 

Cara, isto está, no mínimo, violando 3 dos 5 Vs do Bigdata: 

- *Velocidade*: Já que você está apenas coletando e formando uma massa de dados, pode ser que eles não sejam processados no tempo certo;
- *Veracidade*: Como auditar esse imenso aglomerado de dados, para saber se sua qualidade é boa?
- *Valor*: Que valor pode possuir um aglomerado disforme de dados, cuja análise se torna cada vez mais complexa?

Eu gosto de comparar **Data lakes** com aquele cesto de papel higiênico sujo, que deixamos no banheiro. Desculpem se parece escatológico, mas é a comparação mais válida para mim.

Essa confusão não deixa de ser proposital, afinal de contas, criar um gigantesco repositório consome recursos e é do interesse dos fornecedores, certo? 

Se você precisa guardar dados para analisar posteriormente, não seria melhor criar data warehouses? Os softwares de **BI** já possuem maturidade e sabem muito bem lidar com grandes volumes de dados perenes, enquanto os softwares de **Bigdata** foram pensados para lidar com dados transientes. Talvez fosse mais eficiente pensar em BI e Data warehouse.

## Hadoop

Hadoop é o nome da ferramenta mais conhecida de Bigdata. Ele foi criado em 2006, por Doug Cutting, a partir de outras bibliotecas e softwares open source. O Hadoop é composto por: 
- Hadoop common: utilitários;
- HDFS (Hadoop Distributed File System): Um sistema distribuído de arquivos;
- Hadoop MapReduce: Uma implementação do algoritmo MapReduce, criado pela Google, para agregação de dados;
- Hadoop Yarn: Gestor e agendador de Jobs em clusters.

### Map Reduce

É um algorítmo publicado em 2004 por Jeffrey Dean e Sanjay Ghemawat, dois pesquisadores da Google, voltado para processamento distribuído de grandes volumes de dados. 

Funciona baseado em 3 funções:

- **Map**: Cada entrada é associada a uma chave e quebrada em pedaços menores;
- **Shuffle**: As entradas de cada chave são direcionadas a um mesmo nó;
- **Reduce**: As entradas de cada chave são reduzidas por uma função de agregação. 

Vamos dar um exemplo: Um contador de palavras. Entramos com um arquivo textual: 
```
"Minha terra tem palmeiras,
Onde canta o Sabiá;
As aves, que aqui gorjeiam,
Não gorjeiam como lá.
Nosso céu tem mais estrelas,
Nossas várzeas têm mais flores,
Nossos bosques têm mais vida,
Nossa vida mais amores. "
```
**Map**

Pegamos cada palavra com chave e a contamos: 

```
Minha, 1
terra, 1
tem, 1
palmeiras,1
Onde, 1
canta, 1
o, 1
Sabiá, 1
As, 1
aves, 1
que, 1
aqui, 1
gorjeiam, 1
Não, 1
gorjeiam, 1
como, 1
lá, 1
Nosso, 1
céu, 1
tem, 1
mais, 1
estrelas, 1
Nossas, 1
várzeas, 1
têm, 1
mais, 1
flores, 1
Nossos, 1
bosques, 1
têm, 1
mais, 1
vida, 1
Nossa, 1
vida, 1
mais, 1
amores, 1
```

**Shuffle**

Podemos redistibuir por chave: 

Chave | 1 | 2 | 3 | 4
--- | --- | --- | --- | ---
amores | 1 | - | - | -  
aqui | 1 | - | - | -			
As | 1 | - | - | -			
aves | 1 | - | - | - 
bosques | 1 | - | - | - 			
canta | 1 | - | - | - 
céu | 1 | - | - | - 
como | 1 | - | - | - 			
estrelas | 1 | - | - | -
flores | 1 | - | - | - 
gorjeiam | 1 | 1 | - | -
lá | 1 | - | - | -			
mais | 1 | 1 | 1 | 1
Minha | 1 | - | - | - 
Não | 1 | - | - | -			
Nossa | 1 | - | - | -			
Nossas | 1 | - | - | -
Nosso | 1 | - | - | -			
Nossos | 1 | - | - | -			
o | 1 | - | - | -			
Onde | 1 | - | - | -
palmeiras | 1 | - | - | -
que | 1 | - | - | -			
Sabiá | 1 | - | - | -			
tem | 1 | 1 | - | -		
têm | 1 | 1 | - | -		
terra | 1 | - | - | -			
várzeas | 1 | - | - | -			
vida | 1 | 1 | - | -

**Reduce**

Podemos reduzir a lista de valores de cada chave utilizando uma função de agregação que, no nosso caso é o "sum()", ou seja, vamos somar os valores de cada chave: 

Palavra | Contagem
--- | ---
amores | 1
aqui | 1
As | 1
aves | 1
bosques | 1
canta | 1
céu | 1 
como | 1
estrelas | 1
flores | 1 
gorjeiam | 2 
lá | 1 
mais | 4 
Minha | 1
Não | 1 
Nossa | 1
Nossas | 1
Nosso | 1
Nossos | 1
o | 1 
Onde | 1 
palmeiras | 1
que | 1 
Sabiá | 1 
tem | 2 
têm | 2 
terra | 1
várzeas | 1
vida | 2 
		
Esta é uma maneira simplificada de apresentar o Map Reduce, mas é assim que funciona. Podemos reduzir com soma ou média, as funções mais comuns. Outras opções muito utilizadas são a obtenção do **mínimo** ou **máximo**.

Existem vários nós **mapper** na rede distribuída e vários **reducers**.


## Como instalar e brincar com o Hadoop

Ok, chega de papo furado... Vamos instalar o **Hadoop** e rodar um Job de bigdata. Para rodar esse exemplo, você deve ter pelo menos 4 GB de RAM, ok? 

### Cloudera e HortonWorks

É óbvio que é possível utilizar virtualização para instalar um ecossistema simulado Hadoop. Uma excelente escolha é a “Quickstart VM”, da Cloudera, que pode ser executada em ambientes com Hypervisor, como o VirtualBox, ou utilizando Containers, como o Docker. Porém, exige instalação de softwares adicionais (VirtualBox ou Docker), a configuração pode ser mais complexa (no caso do Docker), trata-se de um pacote Hadoop “customizado” e não o Hadoop básico, e, finalmente, exige um “host” de maior capacidade. 

*Nota → Cloudera, HortonWorks e outras distribuições, são “empacotamentos” dos componentes do ecossistema Hadoop, que incluem contrato de suporte, configurações especiais e até componentes próprios. Sempre existe uma versão gratuita, com limitações. Mas isto não é HADOOP. Se você quer aprender a utilizar o Hadoop e ficar independente de uma distribuição, é melhor aprender com o “bare metal”.*

Uma alternativa atrativa e relativamente menos complexa pode ser instalar o Hadoop em uma estação de trabalho comum. Se você tem pelo menos 4 GB de RAM, pode ter um ambiente mais controlado para simular sua aplicação. 

Podemos instalar o Hadoop, além de alguns de seus componentes, em uma máquina local, como uma estação de trabalho, por exemplo. Porém, devemos ter sempre em mente que tal procedimento é apenas para desenvolvimento, jamais para execução de trabalhos reais ou análise de desempenho. 

*Atenção → Jamais utilize a instalação em máquina local como parâmetro de estimação do ambiente operacional definitivo!*


### Standalone versus pseudo distribuído

Podemos instalar o Hadoop local de duas maneiras diferentes: 
- **Standalone**: O Hadoop é executado como um processo Java normal, sem subir “daemons” e sem utilizar o HDFS. Tudo pode ser simulado, mas não haverá processos servidores rodando (“namenode”, “datanode”, “resourcemanager” e “nodemanager”). Alguns componentes do ecossistema Hadoop não funcionam neste modo, pois esperam encontrar os “daemons”;
- **Pseudo distribuído**: Neste modo, os “deamons” do Hadoop são executados em um único “host”, mas simulando um “cluster” real. Haverá “namenode”, “datanode”, “resourcemanager” e “nodemanager”. E será utilizado o HDFS em vez do file system local do “host”.

**Vantagens e desvantagens de cada modo**

O modo *standalone* é ótimo para estudar os comandos HDFS e a criação de apps de “MapReduce”. Possui baixo “footprint” e pode ser executado em “hosts” de qualquer capacidade. Porém, como não há “daemons” sendo executados, todos os componentes que dependem de IPC, ou seja, dependem de comunicação via “daemons”, se tornarão impossíveis de testar.

O modo *pseudo distribuído* exige algumas configurações posteriores, mas simula um “cluster” Hadoop real, permitindo testar todos os compontentes em um ambiente simulado. Porém, exige maiores recursos do “host” e tem algumas desvantagens, entre elas o uso inconveniente de “ssh”… Os comandos para iniciar o HDFS e o YARN usam SSH para iniciar ou parar os “daemons”. Embora seja possível iniciar cada tipo de “daemon” manualmente, tal procedimento é mais trabalhoso. 

### Instalação Standalone

Nesse primeiro tutorial, vamos "brincar" com o Hadoop standalone. Depois, veremos o modo pseudo distribuído. 

Escolha a versão do Hadoop que deseja instalar. Para este exemplo, estou utilizando o Hadoop 2.8.3. O processo é simples: 
    1. Baixar o Hadoop;
    2. Descomprimir;
    3. Testar com o FS local.

**Baixar o Hadoop**

Acesse a página de “downloads” do Hadoop e baixe o arquivo “tar.gz” binário, por exemplo: 

http://www.apache.org/dyn/closer.cgi/hadoop/common/hadoop-2.8.3/hadoop-2.8.3.tar.gz


**Descomprimir**

Copie para sua pasta “home” (ou qualquer outra pasta onde queira guardar suas ferramentas) e descomprima. 

Nota → Renomeie a pasta do Hadoop para tirar a versão, ou então crie um symlink (Linux). Normalmente ele criará a pasta “hadoop-x.y.x”, mas é melhor usarmos apenas “hadoop”. 

**Testar o Hadoop com o FS local**

Crie a variável de ambiente “HADOOP_HOME” apontando para a pasta do Hadoop. Se você renomeu ou criou “symlink”, então deve ser algo assim: “~/hadoop”. Se você usa MS Windows, procure colocar o caminho completo, incluindo a letra do drive.

Modifique a variável de ambiente “PATH” e coloque a pasta “$HADOOP_HOME/bin” (ou %HADOOP_HOME%\bin, se for windows) nela: 

Linux: 
```
cd
vi ./.bashrc
export HADOOP_HOME=/home/luck/hadoop
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```
Neste caso, não subiremos “daemons” e nem usaremos o HDFS. Na sua pasta “home”, a mesma onde criou a pasta do Hadoop, crie uma pasta: “input”. 

Copie o arquivo "README.txt" da instalação do Hadoop para a pasta "input" e vamos contar as palavras...

Em linux: 
```
cp $HADOOP_HOME/README.txt input
hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.8.3.jar wordcount input output
cat output/*
```
Eis o resultado: 
```
(BIS),	1
(ECCN)	1
(TSU)	1
(see	1
5D002.C.1,	1
740.13)	1
<http://www.wassenaar.org/>	1
Administration	1
Apache	1
BEFORE	1
BIS	1
Bureau	1
Commerce,	1
Commodity	1
Control	1
Core	1
Department	1
ENC	1
Exception	1
Export	2
For	1
Foundation	1
Government	1
Hadoop	1
Hadoop,	1
Industry	1
Jetty	1
License	1
Number	1
Regulations,	1
SSL	1
Section	1
Security	1
See	1
Software	2
Technology	1
The	4
This	1
U.S.	1
Unrestricted	1
about	1
algorithms.	1
and	6
and/or	1
another	1
any	1
as	1
asymmetric	1
at:	2
both	1
by	1
check	1
classified	1
code	1
code.	1
concerning	1
country	1
country's	1
country,	1
cryptographic	3
currently	1
details	1
distribution	2
eligible	1
encryption	3
exception	1
export	1
following	1
for	3
form	1
from	1
functions	1
has	1
have	1
http://hadoop.apache.org/core/	1
http://wiki.apache.org/hadoop/	1
if	1
import,	2
in	1
included	1
includes	2
information	2
information.	1
is	1
it	1
latest	1
laws,	1
libraries	1
makes	1
manner	1
may	1
more	2
mortbay.org.	1
object	1
of	5
on	2
or	2
our	2
performing	1
permitted.	1
please	2
policies	1
possession,	2
project	1
provides	1
re-export	2
regulations	1
reside	1
restrictions	1
security	1
see	1
software	2
software,	2
software.	2
software:	1
source	1
the	8
this	3
to	2
under	1
use,	2
uses	1
using	2
visit	1
website	1
which	2
wiki,	1
with	1
written	1
you	1
your	1

```

**Quer ver o código-fonte?**

O Wordcount é um exemplo que vem com o Hadoop, já pre-compilado. Se quiser ver o código-fonte, ele está em um **jar**: 
$HADOOP_HOME/share/hadoop/mapreduce/sources/hadoop-mapreduce-examples-2.8.3-sources.jar. Eis o fonte da classe Wordcount aqui:
```
/**
 * Licensed to the Apache Software Foundation (ASF) under one
 * or more contributor license agreements.  See the NOTICE file
 * distributed with this work for additional information
 * regarding copyright ownership.  The ASF licenses this file
 * to you under the Apache License, Version 2.0 (the
 * "License"); you may not use this file except in compliance
 * with the License.  You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
package org.apache.hadoop.examples;

import java.io.IOException;
import java.util.StringTokenizer;

import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.util.GenericOptionsParser;

public class WordCount {

  public static class TokenizerMapper 
       extends Mapper<Object, Text, Text, IntWritable>{
    
    private final static IntWritable one = new IntWritable(1);
    private Text word = new Text();
      
    public void map(Object key, Text value, Context context
                    ) throws IOException, InterruptedException {
      StringTokenizer itr = new StringTokenizer(value.toString());
      while (itr.hasMoreTokens()) {
        word.set(itr.nextToken());
        context.write(word, one);
      }
    }
  }
  
  public static class IntSumReducer 
       extends Reducer<Text,IntWritable,Text,IntWritable> {
    private IntWritable result = new IntWritable();

    public void reduce(Text key, Iterable<IntWritable> values, 
                       Context context
                       ) throws IOException, InterruptedException {
      int sum = 0;
      for (IntWritable val : values) {
        sum += val.get();
      }
      result.set(sum);
      context.write(key, result);
    }
  }

  public static void main(String[] args) throws Exception {
    Configuration conf = new Configuration();
    String[] otherArgs = new GenericOptionsParser(conf, args).getRemainingArgs();
    if (otherArgs.length < 2) {
      System.err.println("Usage: wordcount <in> [<in>...] <out>");
      System.exit(2);
    }
    Job job = Job.getInstance(conf, "word count");
    job.setJarByClass(WordCount.class);
    job.setMapperClass(TokenizerMapper.class);
    job.setCombinerClass(IntSumReducer.class);
    job.setReducerClass(IntSumReducer.class);
    job.setOutputKeyClass(Text.class);
    job.setOutputValueClass(IntWritable.class);
    for (int i = 0; i < otherArgs.length - 1; ++i) {
      FileInputFormat.addInputPath(job, new Path(otherArgs[i]));
    }
    FileOutputFormat.setOutputPath(job,
      new Path(otherArgs[otherArgs.length - 1]));
    System.exit(job.waitForCompletion(true) ? 0 : 1);
  }
}

```

## Por hoje, é só...

Continue acompanhando que vou mostrar muitas coisas sobre Bigdata. Isso foi só uma **amostra** do que podemos fazer com essa tecnologia. E, quando você vir coisas realmente legais, como o **Spark**, tenho certeza que vai gostar mais!





