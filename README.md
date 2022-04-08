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

### 3. 
<b>
Como podemos observar en la imagen,
</b>


