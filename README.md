# ⚡ TransNPN - Simulador de Transistor NPN

Aplicação web/mobile completa para análise de polarização de transistores NPN, com suporte a **4 configurações** e visualização gráfica de alta qualidade do ponto de operação.

## 🔧 Tipos de Polarização Suportados

- **Resistor de Base Fixo** (configuração clássica com RB)
- **Divisor de Tensão** (polarização por divisor resistivo)
- **Divisor com Resistor de Emissor** (estabilização térmica com RE)
- **Apenas Resistor de Emissor (RE)** (polarização com RE sem divisor)

## 📥 Parâmetros de Entrada

Cada configuração possui campos específicos:

**Resistor de Base:**
- `VBB` (V) - Tensão da base
- `VCC` (V) - Tensão de alimentação
- `β` (Beta) - Ganho de corrente
- `RB` (Ω) - Resistor de base
- `RC` (Ω) - Resistor de coletor

**Divisor de Tensão:**
- `VCC` (V) - Tensão de alimentação
- `β` (Beta) - Ganho de corrente
- `R1` (Ω) - Resistor superior do divisor
- `R2` (Ω) - Resistor inferior do divisor
- `RC` (Ω) - Resistor de coletor

**Divisor + RE:**
- `VCC` (V) - Tensão de alimentação
- `β` (Beta) - Ganho de corrente
- `R1` (Ω) - Resistor superior do divisor
- `R2` (Ω) - Resistor inferior do divisor
- `RC` (Ω) - Resistor de coletor
- `RE` (Ω) - Resistor de emissor

**Apenas Resistor de Emissor (RE):**
- `VBB` (V) - Tensão da base
- `VCC` (V) - Tensão de alimentação
- `β` (Beta) - Ganho de corrente
- `RB` (Ω) - Resistor de base
- `RC` (Ω) - Resistor de coletor
- `RE` (Ω) - Resistor de emissor

## 📊 Cálculos Realizados

- **Corrente da Base (IB)** - Cálculo considerando a topologia escolhida
- **Corrente do Coletor (IC)** - IC = β × IB (limitada pela saturação)
- **Tensão Coletor-Emissor (VCE)** - Determinada pela reta de carga
- **Potência Dissipada** - P = VCE × IC
- **Ponto Quiescente (Q)** - Coordenadas (VCE, IC) do ponto de operação
- **Região de Operação** - Corte, Ativa ou Saturação

## 📈 Gráfico da Reta de Carga (otimizado para mobile)

O simulador exibe graficamente:
- **Reta de carga** do circuito em destaque
- **Curvas de corrente de base** (IB constante) com valores em µA
- **Ponto Q** destacado (apenas o ponto, coordenadas nos resultados)
- **Alta resolução** (1000×700 pixels) para nitidez em celulares
- **Fontes ampliadas** (24px nos eixos, 20px nos valores de IB)
- **Código de cores**: curva IB do ponto Q em vermelho, demais em azul tracejado
- **Rótulos com fundo branco** para máxima legibilidade

## 🧮 Fórmulas Implementadas

**Resistor de Base:**

  IB = (VBB - 0,7) / RB
  IC = β × IB
  VCE = VCC - (IC × RC)

**Divisor de Tensão (equivalente Thevenin):**

  Vth = VCC × (R2 / (R1 + R2))
  Rth = (R1 × R2) / (R1 + R2)
  IB = (Vth - 0,7) / Rth
  IC = β × IB
  VCE = VCC - IC × RC

**Divisor com RE:**

  IB = (Vth - 0,7) / [Rth + (β + 1) × RE]
  IC = β × IB
  VCE = VCC - IC × (RC + RE)

**Apenas Resistor de Emissor (RE):**

  IB = (VBB - 0,7) / [RB + (β + 1) × RE]
  IC = β × IB
  VCE = VCC - IC × (RC + RE)

**Saturação:**

  ICsat = (VCC - 0,2) / RC
  VCEsat = 0,2 V


## 🚀 Como Usar

1. Faça o download do arquivo `transistor.html`
2. Abra no navegador (funciona perfeitamente no celular)
3. Escolha o tipo de polarização desejado
4. Insira os valores dos componentes
5. Clique em "Calcular" para ver os resultados
6. Use o botão "Limpar" para resetar os campos

## ✨ Funcionalidades

- ✅ **4 topologias de polarização** (nova: apenas RE)
- ✅ Interface 100% responsiva (adaptável a celulares e desktops)
- ✅ Design moderno com cards e cores intuitivas
- ✅ Detecção automática da região de operação
- ✅ **Gráfico de alta resolução** com fontes ampliadas para mobile
- ✅ Curva IB do ponto Q em destaque (vermelho)
- ✅ Rótulos com fundo branco para legibilidade
- ✅ Cálculo em tempo real
- ✅ Botão "Limpar" para reset rápido
- ✅ Funciona offline após baixado

## 📱 Compatibilidade

- Navegadores desktop (Chrome, Firefox, Edge, Safari)
- Dispositivos móveis (iOS e Android) - otimizado para telas pequenas
- Funciona offline após baixado!

## 🎓 Sobre o Projeto

Desenvolvido para a disciplina de **Eletrônica Aplicada I**, este simulador auxilia estudantes a visualizarem o comportamento de transistores bipolares em diferentes configurações de polarização, facilitando a compreensão do ponto de operação e dos limites de cada região.

A versão mais recente inclui melhorias significativas de acessibilidade mobile, com gráfico em alta resolução e fontes ampliadas para melhor visualização em dispositivos móveis.

---

**Autora:** Maria Vitória de Holanda Rocha 
**Disciplina:** Eletrônica Aplicada I  
**Versão:** 3.0 - 4 configurações + gráfico mobile aprimorado  
**Última atualização:** Fevereiro/2026
