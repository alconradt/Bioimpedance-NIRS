# Software Analisador de Impedância e NIRS
## Considerações Iniciais
### Este software embarcado foi escrito para a placa NUCLEO-F303ZE. O sinal utilizado para injeção de corrente no paciente é o DIBS (Discrete Interval Binary Signal), aplicando 28 frequências que variam de 125 Hz até 875 kHz. 3 leds são utilizados na análise NIRS visando atender diferentes tons de pele. 
## DIBS 
### A sequẽncia DIBS foi gerada utilizando a Toolbox Frequency Domain System Identification para software MATLAB, mais informações sobre o funcionamento da ferramenta podem ser encontradas nos links:

https://www.mathworks.com/products/connections/product_detail/frequency-domain-system-identification-toolbox.html

https://lost-contact.mit.edu/afs/it.kth.se/misc/packages/matlab/help/toolbox/fdident/dibs.html

### As frequências escolhidas são múltiplas pelo vetor:  [125, 250, 375, 500, 625, 750, 875] x Ordem da década. 
### No código o DIBS é gerado utilizando DMA para alterar o registrador BSRR da porta PA0. Este DMA é acionado por um Timer afim de garantir a periodicidade do sinal. 
## ADC
### Neste sistema foram utilizados 2 ADC, um para a conversão do sinal DIBS e outro para a conversão de tensão do foto diodo. Aqui destaca-se que o ADC do sinal DIBS é feito por DMA e este DMA é acionado por um Timer afim de garantir uma taxa de aquisição fixa ao sistema. 
