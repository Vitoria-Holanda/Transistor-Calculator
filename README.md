# ⚡ TransNPN - Simulador de Transistor NPN

Aplicação web/mobile completa para análise de polarização de transistores NPN, com suporte a múltiplas configurações e visualização gráfica do ponto de operação.

## 🔧 Tipos de Polarização Suportados

- **Resistor de Base Fixo** (configuração clássica com RB)
- **Divisor de Tensão** (polarização por divisor resistivo)
- **Divisor com Resistor de Emissor** (estabilização térmica com RE)

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
- Adiciona `RE` (Ω) - Resistor de emissor

## 📊 Cálculos Realizados

- **Corrente da Base (IB)** - Cálculo considerando a topologia escolhida
- **Corrente do Coletor (IC)** - IC = β × IB (limitada pela saturação)
- **Tensão Coletor-Emissor (VCE)** - Determinada pela reta de carga
- **Potência Dissipada** - P = VCE × IC
- **Ponto Quiescente (Q)** - Coordenadas (VCE, IC) do ponto de operação
- **Região de Operação** - Corte, Ativa ou Saturação

## 📈 Gráfico da Reta de Carga

O simulador exibe graficamente:
- **Reta de carga** do circuito
- **Curvas de corrente de base** (IB constante)
- **Ponto Q** destacado com coordenadas
- Identificação visual da região de operação

## 🧮 Fórmulas Implementadas

**Resistor de Base:**

  IB = (VBB - 0,7) / RB
  IC = β × IB
  VCE = VCC - IC × RC

**Divisor de Tensão (equivalente Thevenin):**

  Vth = VCC × (R2 / (R1 + R2))
  Rth = (R1 × R2) / (R1 + R2)
  IB = (Vth - 0,7) / Rth

**Divisor com RE:**

 IB = (Vth - 0,7) / [Rth + (β + 1) × RE]

**Saturação:**

  ICsat = (VCC - 0,2) / RC


## 🚀 Como Usar

1. Faça o download do arquivo `transistor.html`
2. Abra no navegador (funciona perfeitamente no celular)
3. Escolha o tipo de polarização desejado
4. Insira os valores componentes
5. Clique em "Calcular" para ver os resultados
6. Use o botão "Exemplo" para testar com valores típicos

## ✨ Funcionalidades

- ✅ Interface responsiva (adaptável a celulares e desktops)
- ✅ Design moderno com cards e cores intuitivas
- ✅ Três topologias de polarização
- ✅ Detecção automática da região de operação
- ✅ Gráfico interativo da reta de carga
- ✅ Valores de exemplo pré-definidos
- ✅ Cálculo em tempo real

## 📱 Compatibilidade

- Navegadores desktop (Chrome, Firefox, Edge, Safari)
- Dispositivos móveis (iOS e Android)
- Funciona offline após baixado

## 🎓 Sobre o Projeto

Desenvolvido para a disciplina de **Eletrônica Aplicada I**, este simulador auxilia estudantes a visualizarem o comportamento de transistores bipolares em diferentes configurações de polarização, facilitando a compreensão do ponto de operação e dos limites de cada região.

---

**Autor:** Maria Vitória de Holanda 
**Disciplina:** Eletrônica Aplicada I  
**Versão:** 2.0 - Com suporte a múltiplas polarizações e gráfico
