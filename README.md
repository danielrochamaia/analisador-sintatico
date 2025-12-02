# Analisador TONTO - Léxico e Sintático

Analisador completo para a linguagem TONTO (Textual Ontology Language), implementando análise léxica e sintática conforme especificações da disciplina de Compiladores.

## 👥 Autores

- Daniel Rocha Maia
- Gabriela de Oliveira Pascoal

## 📋 Sobre o Projeto

Este projeto implementa um compilador frontend completo para a linguagem TONTO, incluindo:
- ✅ **Análise Léxica** (Unidade 1)
- ✅ **Análise Sintática** (Unidade 2)
- 🔜 **Análise Semântica** (Unidade 3 - futuro)

## 🎯 Funcionalidades

### Análise Léxica
- Identificação de 18 estereótipos de classe
- Identificação de 29 estereótipos de relação
- Reconhecimento de palavras reservadas
- Validação de nomes (classes, relações, instâncias)
- Detecção de erros léxicos com sugestões

### Análise Sintática
Conforme critérios da Unidade 2, reconhece:

1. **Declaração de Pacotes**
   ```tonto
   package NomePackage {
       # declarações
   }
   ```

2. **Declaração de Classes**
   ```tonto
   kind Person

   kind Person {
       name: string
       birthdate: date
   }
   ```

3. **Declaração de Tipos de Dados**
   ```tonto
   AddressDataType {
       street: string
       city: string
   }
   ```

4. **Classes Enumeradas**
   ```tonto
   enum EyeColor {
       Blue, Green, Brown, Black
   }
   ```

5. **Generalizações (Gensets)**
   ```tonto
   # Forma simples
   disjoint complete genset PersonAgeGroup where general Person specifics Child Adult

   # Forma completa
   disjoint complete genset PersonAgeGroup {
       general Person
       specifics Child Adult
   }
   ```

6. **Declarações de Relações**
   ```tonto
   # Relação interna
   kind University {
       componentOf <>-- Department
   }

   # Relação externa
   @mediation relation Employee -- EmploymentContract
   ```

### Visualizações

#### 1. Tabela de Síntese
Mostra resumo completo dos construtos encontrados:
- Quantos e quais pacotes
- Quais classes estão em cada pacote
- Quais relações estão em cada classe e quais são externas
- Quantas e quais declarações de tipos
- Generalizações e suas configurações

#### 2. Relatório de Erros
- Lista completa de erros léxicos e sintáticos
- Linha e coluna de cada erro
- Mensagem descritiva do problema
- **Sugestões de correção** para cada erro