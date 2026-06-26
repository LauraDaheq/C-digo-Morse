# Código Morse 📡

Conversor de texto a código Morse usando Arduino con LED en el pin 13.

## Descripción del Proyecto

Este proyecto convierte mensajes de texto en código Morse y los transmite visualmente mediante destellos de LED. Puedes enviar caracteres a través del puerto serial y el LED parpadeará en patrón Morse.

## Componentes Utilizados

- **Arduino UNO**: Microcontrolador principal
- **LED**: Indicador visual (Pin 13 - LED integrado)
- **Resistencia de 1kΩ**: Protección del LED (opcional si usas LED integrado)
- **Puerto Serial USB**: Para enviar mensajes desde la computadora
- **Protoboard**: Para las conexiones

## Características

- ✅ Convierte letras (A-Z) a código Morse
- ✅ Convierte números (0-9) a código Morse
- ✅ Soporta mayúsculas y minúsculas
- ✅ Espacios entre palabras automáticos
- ✅ Comunicación por puerto serial a 9600 baud
- ✅ LED integrado en pin 13

## Pines Utilizados

| Componente | Pin Arduino |
|-----------|------------|
| LED | 13 (LED integrado) |
| USB Serial | RX/TX |

## Código Morse Implementado

### Letras (A-Z)
```
A .-     N -.     
B -...   O ---    
C -.-.   P .--.   
D -..    Q --.-   
E .      R .-.    
F ..-.   S ...    
G --.    T -      
H ....   U ..-    
I ..     V ...-   
J .---   W .--    
K -.-    X -..-   
L .-..   Y -.--   
M --     Z --..   
```

### Números (0-9)
```
0 -----  5 .....
1 .----  6 -....
2 ..---  7 --...
3 ...--  8 ---..
4 ....-  9 ----.
```

## Funcionamiento

1. Sube el código `MORSE.ino` a tu Arduino UNO
2. Abre el Monitor Serial (115200 baud)
3. Escribe un mensaje (letras, números y espacios)
4. El LED parpadeará según el código Morse:
   - **Punto (.)**: Destello corto (200ms)
   - **Raya (-)**: Destello largo (600ms)
   - **Espacio entre símbolos**: 200ms
   - **Espacio entre letras**: 600ms
   - **Espacio entre palabras**: 800ms

## Tabla de Tiempos

| Elemento | Duración |
|----------|----------|
| Punto (.) | 200 ms |
| Raya (-) | 600 ms (3 × punto) |
| Espacio entre símbolos | 200 ms |
| Espacio entre letras | 600 ms |
| Espacio entre palabras | 800 ms |

## Ejemplo de Uso

```
Entrada: "SOS"
Salida LED:
...   ---   ...
(S)   (O)   (S)
```

## Notas Importantes

- El `dotDelay` de 200ms permite una velocidad de ~12 palabras por minuto en código Morse
- Puedes ajustar `dotDelay` para acelerar o desacelerar la transmisión
- El LED integrado del pin 13 no requiere resistencia adicional
- La velocidad del puerto serial es 9600 baud

## Mejoras Posibles

- Agregar un buzzer para sonido además de luz
- Implementar entrada desde botones físicos
- Guardar mensajes en memoria EEPROM
- Mostrar traducción inversa (Morse a texto)
- Control de velocidad por potenciómetro
