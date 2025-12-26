
# Conversiones entre sistemas numéricos

Un dato es la información que recibe la computadora para ser manipulada y estos pueden ser:
 - Números
 - Letras
 - Palabras
 - Etc.

Las computadoras no pueden leer la información tal cual la reciben dado que se tienen que convertir en **bits**.
Un bit es la unidad más pequeña de información y sólo puede tener dos valores: 1 y 0. (on and off).

![[Pasted image 20251202221059.png]]

# Sistemas numéricos
Un sistema numérico es el conjunto de símbolos y reglas usado para representar los números.

## Sistema decimal
- Es en base 10.
- Toma valores según su posición de derecha a izquierda.

## Binario
- Es en base 2.
- 0 y 1

## Octal
- Es en base 8


## Hexadecimal
- Es en base 16
- 0,1,2,3,4,5,6,7,8,9,**A,B,C,D,E,F**
- Éste sistema es más corto que el decimal y por ello se usa actualmente en las computadoras 
Equivalencia de las letras en el sistema decimal:

| Hexadecimal | A   | B   | C   | D   | E   | F   |
| ----------- | --- | --- | --- | --- | --- | --- |
| Decimal     | 10  | 11  | 12  | 13  | 14  | 15  |

![[Pasted image 20251202222047.png]]

# Conversiones entre sistemas

## Binario a decimal

**Número a convertir: 10101010**

1. Escribe de derecha a izquierda los números del 0 al 7.
2. Escribe un montón de 2s debajo de los números.
3. Simula que los números del 0 al 7 son potencias del 2.
4. Resuelve las potencias (básicamente puedes saltarte toda esa basura escribiendo 128, 64, 32, 16, 8, 4, 2, 1)
5. Suma únicamente los números que coincidan con el 1 como en la imagen:
![[Pasted image 20251202222318.png]]

**El resultado es 170.**

## Octal a decimal

**Número a convertir: 412**

1. Exactamente igual que el anterior.
2. Números a acomodar: 64, 8, 1
3. Multiplica 64 por el primer número, 8 por el segundo y 1 para el último y suma los resultados.
![[Pasted image 20251202223321.png]]

**El resultado es 266.**

## Hexadecimal a decimal
![[Pasted image 20251202223852.png]]![[Pasted image 20251202224149.png]]