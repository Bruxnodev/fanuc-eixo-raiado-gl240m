# 📘 Glossário de Comandos CNC - FANUC

Este glossário contém a descrição dos principais comandos e siglas usados no programa CNC `O0010`, voltado para torno com controle **FANUC 0i-TD**.

---

## 🔧 Comandos G (Preparação e Movimento)

| Comando | Significado | Descrição |
|--------|-------------|------------|
| `G0`   | Movimento Rápido | Deslocamento rápido sem corte. Usado para posicionamento. |
| `G1`   | Interpolação Linear | Movimento com avanço programado, usado para usinagem reta. |
| `G2`   | Interpolação Circular Horária | Movimento circular no sentido horário. Utilizado para gerar raios ou arcos. |
| `G3`   | Interpolação Circular Anti-Horária | Movimento circular no sentido anti-horário. |
| `G21`  | Programação em Milímetros | Define a unidade de medida como milímetros. |
| `G90`  | Coordenadas Absolutas | Define que os valores de posição são absolutos (referenciados ao zero da peça). |
| `G95`  | Avanço por Rotação | Define o avanço em mm por rotação do eixo (mm/rot). |
| `G96`  | Velocidade de Corte Constante | Mantém a velocidade de corte constante em m/min. |
| `G92`  | Limite de Rotação | Define um limite máximo para a rotação do eixo-árvore. |
| `G58`  | Sistema de Coordenadas | Ativa o sistema de coordenadas com origem definida pela função G58 (zero peça). |

---

## 🧰 Comandos T (Ferramentas)

| Comando | Significado | Descrição |
|---------|-------------|------------|
| `T0101` | Seleção da Ferramenta e Corretor | T01: ferramenta 1, 01: corretor de geometria 1. |

---

## ⚙️ Comandos M (Funções Miscelâneas)

| Comando | Significado | Descrição |
|---------|-------------|------------|
| `M4`    | Rotação Anti-Horária | Liga o eixo-árvore no sentido anti-horário (padrão para ferramentas externas). |
| `M30`   | Fim de Programa | Finaliza o programa e rebobina para o início. |

---

## 📏 Coordenadas e Eixos

| Letra | Significado | Descrição |
|-------|-------------|------------|
| `X`   | Eixo Horizontal | Define o diâmetro da peça (movimento da ferramenta na horizontal). |
| `Z`   | Eixo Longitudinal | Define o comprimento da peça (movimento da ferramenta ao longo da peça). |
| `R`   | Raio | Utilizado em comandos G2 e G3 para definir o raio do arco. |
| `F`   | Avanço | Velocidade de avanço da ferramenta em mm/rot. |
| `S`   | Velocidade de Corte | Usado com G96 para definir m/min, ou com G97 para RPM (não usado neste programa). |

---

## 🛑 Observações Adicionais

- **Faceamento:** Operação de usinagem para nivelar a extremidade da peça.
- **Desbaste:** Remoção inicial de material em grande volume.
- **Chanfro:** Corte em ângulo reto entre duas superfícies.
- **Cone:** Usinagem cônica entre dois diâmetros.
- **Interpolações G2/G3:** Usadas para criar formas curvas e suaves.
- **Ponto de troca:** Posição segura para troca de ferramenta ou inspeção.

---

## 💡 Dica

Use este glossário como referência ao interpretar ou modificar programas CNC em linguagem ISO, especialmente para torno com controle **FANUC**.

---
