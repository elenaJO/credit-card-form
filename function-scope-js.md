# Trabajo

Identificar las funciones globales, locales, funciones de callback, expresions, statement, clousure, scope, contextos de ejecucion, que funciones forman parte de la pila de ejecucion (stack execution) y que funciones forman parte de la cola de eventos (event queue).

## Funciones Globales

- function activeButton()
- function desactiveButton()
- function longitud(input)
- function soloNumeros(input)
- function isValidCreditCard(numberCard)

## Variables Globales

- var $inputCard = $('#card-number')
- var $inputMonth = $('.input-month')
- var $inputYear = $('.input-year')
- var $buttonNext = $('#next')
- var regexOnlyNumbers = /^[0-9]+$/
- var labelErrorOrSuccessMessages = $('label[for="card-number"]')

## Variable Local

- var creditCardNumber = soloNumeros(longitud(numberCard))
- var arr = []
- var sumaTotal = 0

## Funciones Statement

- function activeButton()
- function desactiveButton()
- function longitud(input)
- function soloNumeros(input)
- function isValidCreditCard(numberCard)

## Funciones callback

- $(document).ready(function() {})
- $inputCard.on('input', function() {});

## Pila de Ejecucion 

- function activeButton()
- function desactiveButton()
- function longitud(input)
- function soloNumeros(input)

## Cola de Eventos

- $inputCard.on('input', function())
- function isValidCreditCard(numberCard)

## Clousure 

Las funciones hacen referencia al Contexto global

- function activeButton()
- function desactiveButton()
- function longitud(input)
- function soloNumeros(input)
- function isValidCreditCard(numberCard)

 La variable regex hace referncia a la funcion soloNumeros

 ```js
 function soloNumeros(input) {
    var regex = /^[0-9]+$/;
    if (regex.test(input)) {
      return input;
    }
  }
 ``` 
Las variables arr,sumaTotal hacen referencia a la función isValidCreditCard

```js
 function isValidCreditCard(numberCard) {
    var creditCardNumber = soloNumeros(longitud(numberCard));
    if (creditCardNumber !== undefined) {
      var arr = [];
      var sumaTotal = 0;
      for (var index = creditCardNumber.length - 1; index >= 0; index--) {
        arr.push(creditCardNumber[index]);
      }
      for (var index = 1; index < arr.length; index = index + 2) {
        arr[index] = arr[index] * 2;
        if (arr[index] >= 10) {
          arr[index] = arr[index] - 9;
        }    
      }
     
      for (var index = 0; index < arr.length; index++) {
        sumaTotal = sumaTotal + parseInt(arr[index]);
      }
     
      if (sumaTotal % 10 === 0) {
        console.log('Es una tarjeta valida');
        activeButton();
      } else {
        console.log('No es un numero valido');
        desactiveButton();
      }
    } else {
      console.log('Verifique el numero de su tarjeta'); 
      desactiveButton();  
    }
  }
``` 



 





