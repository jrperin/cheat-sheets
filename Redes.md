# REDE

## Mascaras de Rede

Notação `CIDR (/n)`, onde "n" é o número de bits 1 (fixos) na máscara.

Em uma máscara /n, os primeiros n bits do endereço IPv4 são fixos, e os restantes (32 – n) bits são utilizados para identificar os hosts dentro dessa sub-rede. Essa divisão determina quantos endereços (ou intervalos) a sub-rede contempla. A máscara em notação decimal (quando aplicável) é construída a partir dos 8 bits = 255, ou quando uma parte dos 8 bits estiver sendo parcialmente fixada, teremos valores diferentes.

A seguir, veja uma tabela com alguns exemplos:

| Máscara | Bits Fixos | Máscara Decimal      | Bits para Hosts | Total de Endereços    | Range de IPs (Exemplo)                     |
|---------|------------|----------------------|-----------------|-----------------------|--------------------------------------------|
| /8      | 8          | 255.0.0.0            | 24              | 2²⁴ = 16.777.216      | Ex: 10.0.0.0 – 10.255.255.255              |
| /16     | 16         | 255.255.0.0          | 16              | 2¹⁶ = 65.536          | Ex: 172.16.0.0 – 172.16.255.255            |
| /24     | 24         | 255.255.255.0        | 8               | 2⁸ = 256              | Ex: 192.168.1.0 – 192.168.1.255            |
| /25     | 25         | 255.255.255.128      | 7               | 2⁷ = 128              | Ex: 192.168.1.0 – 192.168.1.127            |
| /28     | 28         | 255.255.255.240      | 4               | 2⁴ = 16               | Ex: 192.168.1.0 – 192.168.1.15             |
| /32     | 32         | 255.255.255.255      | 0               | 2⁰ = 1                | Ex: 192.168.1.10 (representa um único IP)  |

¹ O total de endereços inclui sempre o endereço de rede e o de broadcast, quando aplicável, o que deixa (Total - 2) para hosts utilizáveis em redes tradicionais.

## Lógica por trás das máscaras:

  Cada incremento na notação (/n para /n+1) diminui pela metade a quantidade de endereços disponíveis na sub-rede, pois um bit a mais é dedicado à identificação de rede.
  Por exemplo:
      Ao passar de /24 (256 endereços) para /25, usamos um bit a mais para a rede, resultando em 128 endereços.
      Da mesma forma, /28 (16 endereços) utiliza 28 bits fixos, deixando 4 bits (16 endereços) para hosts.
  No caso do /32, todos os 32 bits são usados para a identificação de rede, o que significa que só há um endereço: ele geralmente representa um host específico (ou um endpoint) e não uma rede.

**Exemplo /28**
O intervalo não precisa sempre começar em 0.
Quando você trabalha com um bloco /28, isto significa que o tamanho do bloco é de 16 endereços. Assim, o início do intervalo deve estar alinhado a um múltiplo de 16. Por exemplo:

- Se o bloco começa em `192.168.1.0`, o intervalo será de `192.168.1.0` até `192.168.1.15`.
- Se você iniciar em `192.168.1.16`, o intervalo será de `192.168.1.16` até `192.168.1.31`.
- Se começar em `192.168.1.32`, o intervalo será de `192.168.1.32` até `192.168.1.47`, e assim por diante.

## Resumo:

Cada máscara "/n" determina quantos bits são "travados" para identificar a rede e quantos ficam para os endereços dos hosts. O aumento do valor "n" reduz o número total de endereços disponíveis (dividindo o intervalo por 2 a cada bit extra), o que permite a segmentação de uma rede maior em sub-redes menores, atendendo a diferentes necessidades.
