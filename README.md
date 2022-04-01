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
