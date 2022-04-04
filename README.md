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
