### Relatório do Projeto: Controle de Gases em Creche de Suínos

#### 1. **Introdução**

O projeto apresentado visa o monitoramento e controle de gases em uma creche para suínos utilizando um sensor de gás e LEDs para sinalização. O objetivo é garantir a segurança dos animais e do ambiente, acionando diferentes LEDs para indicar o nível de concentração de gases, com base em valores lidos pelo sensor.

#### 2. **Descrição do Código**

O código é escrito para uma placa Arduino e utiliza um sensor de gás analógico. O funcionamento geral do código pode ser dividido em duas partes principais: a configuração dos pinos e a leitura e processamento dos valores do sensor.

##### 2.1. **Configuração Inicial**

- **Pinos Definidos:**
  - `PINO_SGAS` (A1): Pino de entrada analógica conectado ao sensor de gás.
  - `LED_VERDE` (7): LED para indicar condições seguras.
  - `LED_AMARELO` (6): LED para sinalizar alerta.
  - `LED_VERMELHO1` (5) e `LED_VERMELHO2` (4): LEDs para indicar perigo e área contaminada.

- **Função `setup()`:**
  - Configuração dos LEDs como saídas.
  - Inicialização da comunicação serial a 9600 bps para monitoramento e depuração.

##### 2.2. **Leitura e Processamento**

- **Função `loop()`:**
  - Leitura do valor analógico do sensor de gás através da função `analogRead()`.
  - Mapeamento do valor lido para uma faixa de 0 a 100 usando a função `map()`, considerando o intervalo de entrada de 300 a 750.
  - Controle dos LEDs baseado nos valores mapeados:
    - **LED Verde**: Sempre ligado, indicando que o sistema está operacional.
    - **LED Amarelo**: Acende se o valor estiver acima de 30, sinalizando alerta.
    - **LED Vermelho1**: Acende se o valor estiver acima de 50, indicando perigo.
    - **LED Vermelho2**: Acende se o valor estiver acima de 80, indicando uma área contaminada.
  - A função `delay(250)` define um intervalo de 250 milissegundos entre leituras para atualizar o estado dos LEDs.

#### 3. **Análise e Sugestões**

##### 3.1. **Análise do Sistema**

O sistema apresentado é eficaz para monitorar os níveis de gases e sinalizar diferentes estados de alerta utilizando LEDs. A lógica de controle é simples e direta, com níveis de alerta bem definidos e implementados através da comparação dos valores lidos com limiares predefinidos.

##### 3.2. **Possíveis Melhorias**

- **Ajuste dos Limiares:**
  - Os valores de mapeamento e os limiares para os LEDs (30, 50, 80) devem ser ajustados conforme as especificações do sensor e as necessidades específicas da creche de suínos. É importante calibrar os limiares com base em experimentos reais para garantir que as indicações de alerta sejam apropriadas para a segurança dos animais.

- **Calibração do Sensor:**
  - O sensor de gás pode exigir uma calibração inicial para garantir leituras precisas. Este passo não está coberto no código e deve ser realizado antes da implementação final.

- **Sistema de Alarme Adicional:**
  - Em situações críticas (como altos níveis de gás), além dos LEDs, pode ser útil adicionar um sistema de alarme sonoro para uma resposta mais imediata.

- **Monitoramento a Longo Prazo:**
  - Considerar a implementação de um log dos valores de gás para monitoramento a longo prazo e análise de tendências. Isso pode ajudar a prever e prevenir problemas futuros.

- **Manutenção e Verificação Regular:**
  - Implementar um sistema de verificação para garantir que o sensor e os LEDs estejam funcionando corretamente e realizar manutenção regular para evitar falhas.

#### 4. **Conclusão**

O projeto fornece uma solução básica e eficaz para o controle de gases em uma creche para suínos, utilizando LEDs para sinalização. Com algumas melhorias e ajustes, pode ser otimizado para garantir a segurança e o bem-estar dos animais, além de facilitar o gerenciamento do ambiente da creche. É fundamental realizar testes e calibração cuidadosa para assegurar a eficácia e a precisão do sistema.
