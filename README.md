# Powershell-Scripting

### 1. 
<b>
Como podemos observar en la imagen, asignamos un valor a una variable y la contcatenamos con el texto "The number is: " 
empleando el cmdlet Write-Host que nos permite visualización (host), como imprimir texto coloreado como cuando se solicita al usuario la entrada junto con Read-Host.</b>

## EJEMPLO:
<code>
$number = 1
Write-Host "The number is: " $number
</code>

![image](https://user-images.githubusercontent.com/91564342/162498587-71943d03-48d2-4088-9ec2-a3515fdd0a76.png)

### 2. 
<b>
Como podemos observar en la imagen, asignamos un valor a una variable para emplearla como contador para determinar cuantas veces se han de ejecutar una sentencia
</b>

## EJEMPLOS:

### FOR:
Asignamos el valor 5 a la variable repeat para inizializar un for indicando que se repetira la sentencia Write-Host "hello" además de un incremento de +1 en la variable counter si el valor de la variable counter es menor que el valor de la variable repeat  

<code>
[int]$repeat = 5
for ($counter = 0; $counter -lt $repeat; $counter++) {
    Write-Host "hello"
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162506135-4258927e-779c-476a-bf53-07efd466ed89.png)

### WHILE:
En este caso, declaramos 2 variables : repeat = 5 y counter = 0, a continuación, entramos en un bucle while con la condición de que eel valor de counter ha de ser menor que el valor de repeat, si es así, se ejecutará la sentencia Write-Host "hello" y el valor de la variable counter se verá incrementada en +1

<code>
[int]$repeat = 5
[int]$counter = 0
while ($counter -lt $repeat) {
    Write-Host "hello"
    $counter++
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162500039-01b2dfd1-e2b8-4db1-91c0-49da99889f1f.png)

### DO WHILE:
En este caso, declaramos 2 variables : repeat = 5 y counter = 0, a continuación, SOLO por primera vez se ejecutará la sentencia Write-Host "hello" y incremento en +1 en counter sin tener en cuenta ninguna "restricción", acto seguido, solo se volverá a ejecutar esa sentencia más veces si el valor de counter es menor que el valor de repeat

<code>
[int]$repeat = 5
[int]$counter = 0
do {
    Write-Host "hello"
    $counter++
}
while ($counter -lt $repeat) 
</code>

![image](https://user-images.githubusercontent.com/91564342/162500900-12bbb3b1-ef3a-4dec-9623-959aa07ac368.png)

### FOR EACH:
En este caso, $character hace referencia a un caracter de la lista y se ejecutará la sentencia Write-Host $character por cada caracter en la lista,
en el caso siguiente, es el mismo razonamiento pero por cada objeto

<code>
foreach ($character in $stringOfCharacters.ToCharArray()) {
    Write-Host $character
} 

[string]$stringOfCharacters = "PowerShell for Beginners"
$stringOfCharacters.ToCharArray() | ForEach-Object { Write-Host "$_" }
</code>

![image](https://user-images.githubusercontent.com/91564342/162501051-9468947e-1a59-4ff1-8955-a1a29d7e76ff.png)

### 3.1 
<b>
Como podemos observar en la imagen, si a = b, se ejecuta la sentencia
</b>

## EJEMPLOS:

### 1.1:

<code>
if (4 -eq 4) {
    Write-Host "4 is equal to 4"
}
if ("hello" -eq "hello") {
    Write-Host "Both strings are equal to each other"
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162507765-7e9454e1-3eb4-42dc-a0eb-e3b74b07a8f1.png)

### 1.2:
<b>En este caso, simplemente comparamos los valores de variables y si son iguales, se ejecuta la sentencia
</b>

<code>
[int]$x = 10
[int]$y = 10

if ($x -eq $y) {
    Write-Host "the x and y variables are equal to each other"
}
else {
    Write-Host "The x and y variables are NOT equal to each other"
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162508436-706117c4-8d19-4ee9-84cb-1064612fa60c.png)

### 1.3:
<b>En este caso, comparamos un string ("Ian") con el valor de una vairable ($yourName) y si son iguales, se ejecuta la sentencia
</b>

<code>
$yourName = "Ian"

if ($yourName -eq "Ian") {
    Write-Host "Hay my name is Ian too!"
}
else {
    Write-Host "Hi $yourName, nice to meet you!"
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162508880-f35bfc49-6dd1-4bec-8ffd-0bdea2b250c0.png)

### 1.4:
<b>En este caso, obtenemos el valor de un input en el cual el usuario introduce el valor y si su valor equivale a "left", seejecuta  Write-Host "Player typed left", si es "right",  Write-Host "Player typed right" y si no es ninguno de los 2 ,  Write-Host "Player typed something we didn't understand"
</b>

<code>
[string]$playerInput = ""
$playerInput = Read-Host -Prompt "You walk into a room with two doorways. One to the left and one to the right. Type 'left' or 'Right' to walk through one of the doors."

if ($playerInput -eq "left") {
    Write-Host "Player typed left"
}
elseif ($playerInput -eq "right") {
    Write-Host "Player typed right"
}
else {
    Write-Host "Player typed something we didn't understand"
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162509209-0e0284b1-4ef8-4375-a832-578411225b9c.png)

## 3.2:
<b>
Comparación de operaciones
</b>

##EJEMPLOS:

### 2.1:
<b>En este caso, si 5 = 5 , se ejecuta la sentencia
</b>

<code>if (5 -eq 5) {
    #5 is equal to 5
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162509803-f65c2164-c99b-48c6-9fb4-e564aa410317.png)

### 2.2:
<b>En este caso, si 3 no es igual a 4, se ejcuta la sentencia
</b>

<code>
if (3 -ne 4) {
    #3 is not equal to 4
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162510004-7e4fc97c-473f-4229-ad75-283bf9f893a9.png)

### 2.3:
<b>En este caso, si 4 es mayor que 2, se ejeduta la sentencia
</b>
<code>
if (4 -gt 2) {
    #4 is greater than 2
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162510452-6bd1d7a8-41e0-47e9-955d-ac4f69c42d43.png)


### 2.4:
<b>En este caso, si 2 es mayor o igual a 1, se ejecuta la sentencia
</b>

<code>
if (2 -ge 1) {
    #2 is greater than or equal to 1
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162510401-2a2c9adc-b530-4853-b200-df42a8eb2188.png)

### 2.5:
<b>En este caso, se ejecutará la sentencia si 1 es menor que 2
</b>
<code>
if (1 -lt 2) {
    #1 is less than 2
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162510700-11c89d3a-cc14-4e1d-bbdf-4f54ae230e3a.png)

### 2.6:
<b>En este caso, si 1 es menor o igual que 2, se ejecuta la sentencia
</b>

<code>
if (1 -le 2) {
    #1 is less than or equal to 2
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162510946-c54c7958-f0b2-49d7-8d6a-40cd3af5936d.png)

## 3.3:
<b>
Comparación con match,like,in,contains
</b>

##EJEMPLOS:

### 3.1:
<b>En este caso, si el primer string empieza por "hello", se ejecuta la sentencia ( * = cualquier carácter)
</b>

<code>
if ("hello how are you?" -like "hello*") {
    #use a wildcard character * to match strings
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162511520-f0eb5fe5-ec43-41a4-925c-4bb549887d5f.png)

### 3.2:
<b>A diferencia de la comparativa anterior, en este caso solo se ejecutará la sentencia si el primer string no empieza por "BYE"
</b>
<code>
if ("HELLO" -notlike "BYE") {
    #HELLO is not like BYE
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162512433-74754d3e-6f88-4b8a-a70e-2d2e49c8a39c.png)

### 3.3:
<b>
Si el caracter "H" se encuentra en el string "HELLO", se ejecutará la sentencia
</b>
<code>
if ("HELLO" -match "H") {
    #H exists in the 
    string "HELLO"
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162512290-18df23ef-1e2a-4566-b0e0-e401948b49e1.png)

### 3.4:
<b>
En este caso, a diferencia del anterior, si el carácter "A" no es encuentra en el string "HELLO", seejecutará la sentencia
</b>

<code>
if ("HELLO" -notmatch "A") {
    #A does not match in the 
    string "HELLO"
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162513247-0131f27b-7eb6-4400-a5a8-ef5ba624d843.png)

### 3.5:
<b>Primeramente, se asigna un valor a la variable $list y si $list contiene el número 3, se ejecutará la sentencia
</b>

<code>
$list = @(1, 2, 3, 4, 5)
if ($list -contains 3) {
    #the list does contain a 3
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162514263-58f3af0a-525f-408d-adc3-b6d3d7b75722.png)

### 3.6:
<b>Primeramente, se asigna un valor a la variable $list y si $list no contiene el número 8, se ejecutará la sentencia
</b>
<code>
$list = @(1, 2, 3, 4, 5)
if ($list -notcontains 8) {
    #$list does not contain 8
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162515303-5420d4ff-1b80-4131-9587-c991aedea40e.png)

### 3.7:
<b>Primeramente, se asigna un valor a la variable $list y si $list contiene el número 3, se ejecutará la sentencia
</b>

<code>
$list = @(1, 2, 3, 4, 5)
if (3 -in $list) {
    #the list does contain a 3
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162515484-9ef2e924-3f0c-4fb2-986e-838a40fb8ac6.png)

### 3.8:

<b>Primeramente, se asigna un valor a la variable $list y si $list no contiene el número 6, se ejecutará la sentencia
</b>

<code>
$list = @(1, 2, 3, 4, 5)
if (6 -notin $list) {
    #6 is not in the list
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162515615-bfa00613-18fc-4317-9764-49e9de64b60f.png)

### 3.9:
<b>Primeramente, se asigna un valor a la variable $var y si $var es un string, se ejecutará la sentencia
</b>

<code>
$var = "This is a string"
if ($var -is [string]) {
    #The variable is a string
}
</code>

![image](https://user-images.githubusercontent.com/91564342/162515771-4869ad91-2e93-43d5-8e26-bd7ef0472ea2.png)

### 3.10:
<b>Primeramente, se asigna un valor a la variable $var y si $var no es un booleano, se ejecutará la sentencia
</b>

<code>
$var = "This is a string"
if ($var -isnot [bool]) {
    #The variable is a string and not a Boolean value so results in true.
} 
</code>

![image](https://user-images.githubusercontent.com/91564342/162515960-e82144bd-1bdc-4779-871a-38d51bcb308e.png)


