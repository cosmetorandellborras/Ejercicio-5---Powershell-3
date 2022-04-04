# Ejercicio-5---Powershell-3

## Objetivos

Los objetivos de esta práctica son analizar y documentar los siguientes 3 scripts de PowerShell

## Acciones previas

Por defecto PowerShell no permite la ejecucion de scripts, para poder ejecutarlos deberemos de seguir estos pasos:

1. Comprobar las restricciones actuales sobre la ejecución de scripts mediante el siguiente cmdlet:
~~~
Get-ExecutionPolicy
~~~
2. En caso de que nos retorne el estado de restriccio "Restricted", cambiar a "Unrestricted" mediante el siguiente comando y aceptar.
~~~
Set-ExecutionPolicy Unrestricted
~~~
![Set-Exec](https://github.com/cosmetorandellborras/Ejercicio-5---Powershell-3/blob/main/Set-Exec.png)

A partir de este momento ya podremos ejecutar scripts en PowerShell

## Ejercicio 1

Código y comentarios del script
~~~
<#Se declara una variable de tipo entero que contendrá el valor 1 #>
$number = 1

<#Se escribe por consola el string "El numero es: " seguido de la variable#>
Write-Host "The number is: " $number

<#Se declara una variable de tipo entero que contendrá el valor 2 #>
$number = 2

<#Se escribe por consola el string "El numero es: " seguido de la variable#>
Write-Host "The number is: " $number

<#Se declara una variable de tipo entero que contendrá el valor 3 #>
$number = 3

<#Se escribe por consola el string "El numero es: " seguido de la variable#>
Write-Host "The number is: " $number

<#Se declara una variable de tipo entero que contendrá el valor 4 #>
$number = 4

<#Se escribe por consola el string "El numero es: " seguido de la variable#>
Write-Host "The number is: " $number
~~~

![Ex1](https://github.com/cosmetorandellborras/Ejercicio-5---Powershell-3/blob/main/Ex1.png)

## Ejercicio 2

Código y comentarios del script

~~~
# Se crea una variable llamada repeat, a la que se le hace un cast a integer y tendrá el valor 5
[int]$repeat = 5

# Mediante un bucle for, se escribira por pantalla "hello" 5 veces, hasta que contador sea igual a 5, ya que en cada vuelta al bucle contador se incrementa en 1
for ($counter = 0; $counter -lt $repeat; $counter++) {
    Write-Host "hello"
} 


# Mediante un bucle while, mientras contador sea menor a repeat, se escribira por pantalla "hello", en cada vuelta al bucle contador se incrementará en 1
[int]$repeat = 5
[int]$counter = 0

while ($counter -lt $repeat) {
    Write-Host "hello"
    $counter++
}


# Mediante un bucle do while, la primera vez se ejecutara y después continuará mientras contador sea menor a repeat, en cada vuelta al bucle contador se incrementará en 1
[int]$repeat = 5
[int]$counter = 0
do {
    Write-Host "hello"
    $counter++
}
while ($counter -lt $repeat) 


# ForEach Loop
# Each time around the loop the $character variable becomes the next character in the list until there are no characters left.

# Se declara una variable de tipo string
[string]$stringOfCharacters = "PowerShell for Beginners"

# Se ejecuta un bucle ForEach, por cada vuelta que dara el bucle la variable character se convierte en la ultima letra del string y se imprime por pantalla
foreach ($character in $stringOfCharacters.ToCharArray()) {
    Write-Host $character
} 

# Se ejecuta un bucle ForEach-Object por cada vuelta que dara el bucle se imprimira por pantalla el carácter en el que se encuentra.
[string]$stringOfCharacters = "PowerShell for Beginners"

$stringOfCharacters.ToCharArray() | ForEach-Object { Write-Host "$_" }
~~~

![Ex2](https://github.com/cosmetorandellborras/Ejercicio-5---Powershell-3/blob/main/Ex2.png)

## Ejercicio 3

Código y comentarios del script

~~~
# Si 4 es igual a 4, se ejecutará lo que esta entre corchetes
if (4 -eq 4) {
    Write-Host "4 is equal to 4"
}

#Si el string "hello" es igual al string "hello", se ejecutará lo que esta entre corchetes
if ("hello" -eq "hello") {
    Write-Host "Both strings are equal to each other"
} 

# Se declaran dos variables de tipo integer con valores 10 / 10 respectivamente
[int]$x = 10
[int]$y = 10

# Si las dos variables son iguales, se ejecutará lo que esta entre corchetes
if ($x -eq $y) {
    Write-Host "the x and y variables are equal to each other"
}
# Si las dos variables no son iguales, se ejecutara lo que esta entre corchetes
else {
    Write-Host "The x and y variables are NOT equal to each other"
}

# Se declara una variable, que tendra por string el valor "Ian"
$yourName = "Ian"

# Si el valor de la variable es igual a "Ian", se ejecutará lo que esta entre corchetes
if ($yourName -eq "Ian") {
    Write-Host "Hay my name is Ian too!"
}
 # En caso de que no se de la confición anterior, se ejecutara lo que esta entre corchetes.
else {
    Write-Host "Hi $yourName, nice to meet you!"
}


#Se crea la variable playerInput, que será de tipo string y inicialmente estará vacia
[string]$playerInput = ""

#Se imprime por pantalla un mensaje y se espera que el usuario introduzca un valor
$playerInput = Read-Host -Prompt "You walk into a room with two doorways. One to the left and one to the right. Type 'left' or 'Right' to walk through one of the doors."

# Si lo que ha introducido el usuario es igual a "left", se ejecutará lo que esta entre corchetes
if ($playerInput -eq "left") {
    Write-Host "Player typed left"
}
# Si lo que ha introducido el usuario es igual a "right", se ejecutará lo que esta entre corchetes
elseif ($playerInput -eq "right") {
    Write-Host "Player typed right"
}
# En caso de que no se cumpla ninguna de las dos opciones anteriores, se ejecutará lo que ensta entre corchetes
else {
    Write-Host "Player typed something we didn't understand"
}


# Operadores de comparación

# -eq	Equals, compara si el valor 5 es igual a 5	
if (5 -eq 5) {
    #5 is equal to 5
}
   
# -ne Not equals, compara si el valor 3 no es igual a 4
if (3 -ne 4) {
    #3 is not equal to 4
}
   
# -gt Greater than, compara si el valor 4 es mas grande que 2
if (4 -gt 2) {
    #4 is greater than 2
}
   
# -ge Greater than or equal, compara si el valor 2 es mayor o igual a 1
if (2 -ge 1) {
    #2 is greater than or equal to 1
}
   
# -lt Less than, compara si el valor 1 es mas pequeño que 2
if (1 -lt 2) {
    #1 is less than 1
}

# -le Less than or equal, compara si el valor 1 es mas pequeño o igual a 2
if (1 -le 2) {
    #1 is less than or equal to 2
} 

# -like nos compara si la cadena inicial empieza por la cadena a comparar, el comodín nos permite solo introducir la parte que queremos comparar y no el resto
if ("hello how are you?" -like "hello*") {
    #use a wildcard character * to match strings
}

# -notlike, compara si el string inicial no es igual string a comparar	
if ("HELLO" -notlike "BYE") {
    #HELLO is not like BYE
} 

# -match, nos compara si dentro del string inicial existe el string secundario
if ("HELLO" -match "H") {
    #H exists in the 
    Write-Host "H exists in the string HELLO"
}
   
# -notmatch, nos compara si dentro del string incial no existe el string secundario	
if ("HELLO" -notmatch "A") {
    #A does not match in the 
    Write-Host "A does not match in the string HELLO"
}

# -contains	nos retorna true si dentro de la lista esta el valor indicado
$list = @(1, 2, 3, 4, 5)
if ($list -contains 3) {
    #the list does contain a 3
}

# -notcontains, nos retorna true si dentro de la lista no esta el valor indicado
$list = @(1, 2, 3, 4, 5)
if ($list -notcontains 8) {
    #$list does not contain 8
}

# -in, nos retorna true si dentro de la lista contiene el valor indicado
$list = @(1, 2, 3, 4, 5)
if (3 -in $list) {
    #the list does contain a 3
} 

# -notin, nos retorna true si dentro de la lista no contiene el valor indicado
$list = @(1, 2, 3, 4, 5)
if (6 -notin $list) {
    #6 is not in the list
}

# -is, nos retorna true si el valor indicado concide con el tipo de valor	
$var = "This is a string"
if ($var -is [string]) {
    #The variable is a string
}

# -isnot, nos retorna true si el valor indicado no conincide con el tipo de valor indicado	
$var = "This is a string"
if ($var -isnot [bool]) {
    #The variable is a string and not a Boolean value so results in true.
} 
   

# Declaraciones Switch
# Se declara una variable de tipo integer con valor 2
[int]$number = 2

# Se ejecutará la condicion 2, que es la que coincide con la variable anterior
switch ($number) {
    1 { "The number is one" }
    2 { "The number is two" }
    default { "I dont know what the number is" }
}


# Se declara una variable de tipo string con el valor "Blue" 

[string]$favouriteColour = "Blue"

# Se ejecutara la condicion que coincida con el valor de la variable anterior, en este caso, lo que esta entre corchetes de la opción "Blue"
switch ($favouriteColour) {
    "Red" {
        "Your favourite colour is Red"
        "I like red too."
    }
 
    "Blue" {
        "Your favourite colour is Blue"
        "I like Blue too."
    }
 
    default { "I dont recognise that colour" }
}
~~~

