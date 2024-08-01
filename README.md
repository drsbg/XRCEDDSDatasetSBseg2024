# Título: Detecção de Intrusões na Internet das Coisas (IoT): Um Ambiente de Experimentação para Obtenção de Dados Reais sobre Protocolos Emergentes

Resumo: Nos ultimos anos, o crescimento exponencial do paradigma da Internet das Coisas (IoT) tem sido impulsionado por industrias como saúde, agricultura e cidades inteligentes. A comunicacão eficiente entre dispositivos, especialmente em ambientes com recursos computacionais limitados, e um desafio constante. Novos protocolos, como o Zenoh e o Data Distribution Service(DDS), tem surgido para atender a essas demandas, oferecendo alta performance e recursos avançados para sistemas distribuídos e em larga escala. No entanto, a literatura carece de datasets publicos para protocolos como Zenoh e DDS XRCE (eXtremely Resource Constrained Environments), limitando as pesquisas em desempenho e segurança. Este trabalho apresenta o desenvolvimento de um dataset detalhado sobre o desempenho desses protocolos em diversos cenarios de comunicacação, fornecendo um recurso valioso para futuras pesquisas em comunicação em tempo real em sistemas IoT.

## Descrição dos Artefatos

O artefato consiste em dois conjuntos de dados (datasets) em formato CSV, gerados a partir da captura de tráfego de rede em um ambiente de teste (testbed) configurado para simular um ambiente típico de comunicação em IoT. Os datasets incluem dados sobre o desempenho do protocolo DDS XRCE em diferentes cenários de comunicação, com e sem acesso à Internet. Os dados foram processados utilizando a ferramenta CICFlowMeter, que extrai fluxos de rede e calcula mais de 80 atributos de fluxo, permitindo análises detalhadas do tráfego de rede.

## Conteúdo dos Datasets

* monitory_envio-rede-aberta.csv: Contém dados coletados em um cenário com acesso à internet, incluindo tráfego de dispositivos residenciais como smartphones, computadores e TVs.

* monitory_envio-rede-isolada.csv: Contém dados coletados em um cenário sem acesso à internet, livre de interferências de tráfego externo.

## Cenário de Teste

Para a prova de conceito, o cenário implementado é uma versão simplificada do cenário completo. Ele consiste em três nós sensores ESP8266, um agente em um notebook Windows e um notebook adicional para monitoramento e captura de dados. Os três ESP8266 atuam como nós sensores, enviando dados simulados de data/hora, temperatura e umidade para o agente, que executa o Micro XRCE-DDS Agent e publica esses dados no tópico DDS "SensorData". O monitoramento e a coleta de dados são realizados com o Wireshark e os dados coletados são processados pelo CICFlowMeter.


## Estrutura dos Dados

Ambos os datasets apresentam a mesma estrutura, com mais de 80 colunas representando os atributos de fluxo calculados pelo CICFlowMeter. Alguns dos atributos mais relevantes incluem:

- Flow Duration: Duração do fluxo de rede em microssegundos.
Total Fwd Packets: Número total de pacotes enviados na direção de ida.
- Total Backward Packets: Número total de pacotes enviados na direção de volta
- Total Length of Fwd Packets: Tamanho total dos pacotes enviados na direção de ida.
- Total Length of Bwd Packets: Tamanho total dos pacotes enviados na direção de volta.
- Fwd Packet Length Max: Tamanho máximo de um pacote enviado na direção de ida
- Fwd Packet Length Min: Tamanho mínimo de um pacote enviado na direção de ida.
- Bwd Packet Length Max: Tamanho máximo de um pacote enviado na direção de volta.
- Bwd Packet Length Min: Tamanho mínimo de um pacote enviado na direção de volta
- Flow Bytes/s: Taxa de transferência do fluxo em bytes por segundo
- Flow Packets/s: Taxa de transferência do fluxo em pacotes por segundo.
- Flow IAT Mean: Tempo médio entre a chegada de pacotes consecutivos no fluxo
- Flow IAT Std: Desvio padrão do tempo entre a chegada de pacotes consecutivos no fluxo
- Flow IAT Max: Maior tempo entre a chegada de pacotes consecutivos no fluxo
- Flow IAT Min: Menor tempo entre a chegada de pacotes consecutivos no fluxo
- Fwd IAT Total: Soma de todos os tempos entre a chegada de pacotes consecutivos na direção de ida
- Bwd IAT Total: Soma de todos os tempos entre a chegada de pacotes consecutivos na direção de volta
- Fwd IAT Mean: Média de todos os tempos entre a chegada de pacotes consecutivos na direção de ida
- Bwd IAT Mean: Média de todos os tempos entre a chegada de pacotes consecutivos na direção de volta
- Fwd IAT Std: Desvio padrão de todos os tempos entre a chegada de pacotes consecutivos na direção de ida
- Bwd IAT Std: Desvio padrão de todos os tempos entre a chegada de pacotes consecutivos na direção de volta
- Fwd IAT Max: Maior tempo entre a chegada de pacotes consecutivos na direção de ida
- Bwd IAT Max: Maior tempo entre a chegada de pacotes consecutivos na direção de volta
- Fwd IAT Min: Menor tempo entre a chegada de pacotes consecutivos na direção de ida
- Bwd IAT Min: Menor tempo entre a chegada de pacotes consecutivos na direção de volta
- Fwd Header Length: Tamanho total dos cabeçalhos dos pacotes enviados na direção de ida
- Bwd Header Length: Tamanho total dos cabeçalhos dos pacotes enviados na direção de volta
- Fwd Packets/s: Taxa de transferência de pacotes na direção de ida
- Bwd Packets/s: Taxa de transferência de pacotes na direção de volta
- Min Packet Length: Tamanho do menor pacote observado no fluxo
- Max Packet Length: Tamanho do maior pacote observado no fluxo
- Packet Length Mean: Tamanho médio dos pacotes no fluxo
- Packet Length Std: Desvio padrão dos tamanhos dos pacotes no fluxo
- Packet Length Variance: Variância dos tamanhos dos pacotes no fluxo
- FIN Flag Count: Número de pacotes com a flag FIN definida
- SYN Flag Count: Número de pacotes com a flag SYN definida
- RST Flag Count: Número de pacotes com a flag RST definida
- PSH Flag Count: Número de pacotes com a flag PSH definida
- ACK Flag Count: Número de pacotes com a flag ACK definida
- URG Flag Count: Número de pacotes com a flag URG definida
- CWE Flag Count: Número de pacotes com a flag CWE definida
- ECE Flag Count: Número de pacotes com a flag ECE definida
- Down/Up Ratio: Proporção entre o número de pacotes na direção de volta e na direção de ida
- Average Packet Size: Tamanho médio dos pacotes no fluxo
- Avg Fwd Segment Size: Tamanho médio dos segmentos na direção de ida
- Avg Bwd Segment Size: Tamanho médio dos segmentos na direção de volta
- Fwd Header Length.1: Tamanho total dos cabeçalhos na direção de ida
- Subflow Fwd Packets: Número de pacotes na direção de ida no subfluxo
- Subflow Fwd Bytes: Número de bytes na direção de ida no subfluxo
- Subflow Bwd Packets: Número de pacotes na direção de volta no subfluxo
- Subflow Bwd Bytes: Número de bytes na direção de volta no subfluxo
- Init_Win_bytes_forward: Tamanho da janela de recepção inicial na direção de ida
- Init_Win_bytes_backward: Tamanho da janela de recepção inicial na direção de volta
- act_data_pkt_fwd: Número de pacotes com payload na direção de ida
- min_seg_size_forward: Tamanho mínimo de segmento na direção de ida
- Active Mean: Média dos períodos de tempo em que ambos os lados do fluxo enviaram pacotes
- Active Std: Desvio padrão dos períodos de tempo em que ambos os lados do fluxo enviaram pacotes
- Active Max: Maior período de tempo em que ambos os lados do fluxo enviaram pacotes
- Active Min: Menor período de tempo em que ambos os lados do fluxo enviaram pacotes
- Idle Mean: Média dos períodos de tempo em que nenhum pacote foi enviado em ambas as direções
- Idle Std: Desvio padrão dos períodos de tempo em que nenhum pacote foi enviado em ambas as direções
- Idle Max: Maior período de tempo em que nenhum pacote foi enviado em ambas as direções
- Idle Min: Menor período de tempo em que nenhum pacote foi enviado em ambas as direções
