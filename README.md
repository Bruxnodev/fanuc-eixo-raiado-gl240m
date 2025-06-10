 Programa CNC: Eixo Escalonado com Raios – FANUC 0i-TD | ROMI GL240M

Este programa realiza a usinagem de um eixo escalonado com raios em torno CNC modelo **ROMI GL240M**, utilizando controle **FANUC 0i-TD**. O ciclo inclui faceamento, desbaste longitudinal, interpolações circulares (raios), chanfros e cone, finalizando com o retorno seguro da ferramenta.

## 📌 Informações Gerais

- **Controle CNC:** FANUC 0i-TD  
- **Máquina:** ROMI GL240M  
- **Ferramenta ativa:** T0101 (Desbaste Pastilha W)  
- **Sistema de coordenadas:** G58 (zero peça)  
- **Modo de programação:** Métrico (G21), coordenadas absolutas (G90), avanço em mm/rotação (G95)

---

## 🛠️ Estrutura do Programa

### 🔒 Bloco de Segurança e Inicialização

```gcode
N10 G21 G90 G95     ; Configurações iniciais (mm, coordenadas absolutas, avanço mm/rot)
N20 T0101           ; Seleção da ferramenta 1 com corretor 1
N30 G96 S250 M4     ; Velocidade de corte constante de 250 m/min, rotação anti-horária
N40 G92 S3000       ; Limite de rotação em 3000 RPM
N50 G58             ; Corretor de origem da peça (zero peça)
🔧 Faceamento Inicial
N60 G0 Z1.5         ; Aproximação em Z
N70 X47             ; Aproximação em X
N80 G1 X-1.6 F.15   ; Faceamento até X=-1.6 mm
N90 G0 X47 Z3.5     ; Recuo rápido
N100 Z0             ; Reposiciona em Z
N110 G1 X-1.6       ; Faceamento final
N120 G0 X35 Z2      ; Reposiciona para início do desbaste
✂️ Desbaste do Contorno Externo
N130 G1 Z-50 F.25       ; Desbaste longitudinal
N140 G2 X41 Z-53 R3     ; Raio externo com interpolação circular horária
N150 G0 Z2              ; Recuo
N160 X31                ; Posição intermediária
N170 G1 Z-38            ; Usinagem linear
N180 G3 X35 Z-40 R2     ; Raio com interpolação anti-horária
N190 G0 Z2              ; Recuo
N200 X27                ; Nova aproximação
N210 G1 Z-25            ; Usinagem linear
N220 X31 Z-27           ; Chanframento
N230 G0 Z2              ; Recuo
N240 X25                ; Aproximação final
N250 G1 Z0              ; Retorno ao início da peça
N260 X27 Z-15           ; Usinagem de cone
✅ Retorno e Finalização
N270 G0 X200            ; Recuo de segurança em X
N280 Z150               ; Recuo de segurança em Z
N290 M30                ; Finaliza o programa e rebobina
