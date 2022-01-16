# Principales Regex (JavaScript)

Hola, en esta ocasión les quiero dejar una lista con las principales **Expresiones Regulares para validar formularios en JavaScript**.

- [Principales Regex (JavaScript)](#principales-regex-javascript)
  - [Dígitos](#dígitos)
  - [Caracteres alfabéticos](#caracteres-alfabéticos)
  - [Caracteres alfanuméricos](#caracteres-alfanuméricos)
  - [Nombre](#nombre)
  - [Email](#email)
  - [Seguridad de la contraseña](#seguridad-de-la-contraseña)
  - [Nombre de usuario](#nombre-de-usuario)
  - [URL](#url)
  - [Dirección IP](#dirección-ip)
  - [Fechas](#fechas)
  - [Tiempo](#tiempo)
  - [Etiquetas HTML](#etiquetas-html)
  - [Controladores de JavaScript](#controladores-de-javascript)
  - [Slug](#slug)
  - [Coincidir duplicados en una cadena](#coincidir-duplicados-en-una-cadena)
  - [Números de teléfono](#números-de-teléfono)
  - [Ruta de archivo](#ruta-de-archivo)
- [jQuery Validation](#jquery-validation)
  - [Scripts requeridos](#scripts-requeridos)
  - [Referencia de reglas](#referencia-de-reglas)
  - [Reglas personalizadas](#reglas-personalizadas)
  - [Eliminar espacios en blanco](#eliminar-espacios-en-blanco)
  - [Llenar al menos uno de varios campos](#llenar-al-menos-uno-de-varios-campos)
  - [Enviar controlador](#enviar-controlador)
- [Ajax](#ajax)
  - [Estructura](#estructura)

## Dígitos

- Números naturales –
`/^[1-9][0-9]*$/`

- Números enteros – `/^-\d+$/`

- Números decimales positivos – `/^\d*\.\d+$/`

- Números enteros + Números decimales – `/^\d*(\.\d+)?$/`

- Negativo, Entero positivo + Números decimales – `/^-?\d*(\.\d+)?$/`

- Entero + Decimal + Fracciones – `/[-]?[0-9]+[,.]?[0-9]*([\/][0-9]+[,.]?[0-9]*)*/`

- Dinero (decimales positivos con punto) – `/(^\d*\.?\d*[0-9]+\d*$)|(^[0-9]+\d*\.\d*$)/`

## Caracteres alfabéticos

- Alfabético sin espacio – `/^[A-Za-z]+$/`

- Alfabético con espacio – `/^[a-zA-Z\s]*$/`

## Caracteres alfanuméricos
- Alfanumérico sin espacio – `/^[a-zA-Z0-9]*$/`

- Alfanumérico con espacio – `/^[a-zA-Z0-9 ]*$/`

## Nombre

- Nombre sin números y permite acentos – `/^[a-zA-ZÀ-ÿ\u00f1\u00d1]+(\s*[a-zA-ZÀ-ÿ\u00f1\u00d1]*)*[a-zA-ZÀ-ÿ\u00f1\u00d1]+$/`

## Email

- Correo electrónico común – `/^([a-zA-Z0-9._%-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6})*$/`

- Alternativa – `/^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/`

- Correo electrónico no común – `/^([a-z0-9_\.\+-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Seguridad de la contraseña

- Moderado: debe tener 1 letra minúscula, 1 letra mayúscula, 1 número y tener al menos 8 caracteres – `/(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/`

## Nombre de usuario

- Cadena alfanumérica que puede incluir _ y - con una longitud de 3 a 16 caracteres – `/^[a-z0-9_-]{3,16}$/`

## URL

- HTTP(S) – `/https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#()?&//=]*)/`

- Protocolo opcional – `/(https?:\/\/)?(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&//=]*)/`

## Dirección IP

- IPv4 – `/^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$/`

- IPv6 – `/(([0-9a-fA-F]{1,4}:){7,7}[0-9a-fA-F]{1,4}|([0-9a-fA-F]{1,4}:){1,7}:|([0-9a-fA-F]{1,4}:){1,6}:[0-9a-fA-F]{1,4}|([0-9a-fA-F]{1,4}:){1,5}(:[0-9a-fA-F]{1,4}){1,2}|([0-9a-fA-F]{1,4}:){1,4}(:[0-9a-fA-F]{1,4}){1,3}|([0-9a-fA-F]{1,4}:){1,3}(:[0-9a-fA-F]{1,4}){1,4}|([0-9a-fA-F]{1,4}:){1,2}(:[0-9a-fA-F]{1,4}){1,5}|[0-9a-fA-F]{1,4}:((:[0-9a-fA-F]{1,4}){1,6})|:((:[0-9a-fA-F]{1,4}){1,7}|:)|fe80:(:[0-9a-fA-F]{0,4}){0,4}%[0-9a-zA-Z]{1,}|::(ffff(:0{1,4}){0,1}:){0,1}((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.){3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])|([0-9a-fA-F]{1,4}:){1,4}:((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.){3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9]))/`

- Ambos – `/((^\s*((([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5]))\s*$)|(^\s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3})|:))|(([0-9A-Fa-f]{1,4}:){4}(((:[0-9A-Fa-f]{1,4}){1,3})|((:[0-9A-Fa-f]{1,4})?:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){3}(((:[0-9A-Fa-f]{1,4}){1,4})|((:[0-9A-Fa-f]{1,4}){0,2}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){2}(((:[0-9A-Fa-f]{1,4}){1,5})|((:[0-9A-Fa-f]{1,4}){0,3}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){1}(((:[0-9A-Fa-f]{1,4}){1,6})|((:[0-9A-Fa-f]{1,4}){0,4}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(:(((:[0-9A-Fa-f]{1,4}){1,7})|((:[0-9A-Fa-f]{1,4}){0,5}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:)))(%.+)?\s*$))/`

## Fechas

- YYYY-MM-dd – `/([12]\d{3}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01]))/`

- dd-MM-YYYY | dd.MM.YYYY | dd/MM/YYYY – `/^(?:(?:31(\/|-|\.)(?:0?[13578]|1[02]))\1|(?:(?:29|30)(\/|-|\.)(?:0?[1,3-9]|1[0-2])\2))(?:(?:1[6-9]|[2-9]\d)?\d{2})$|^(?:29(\/|-|\.)0?2\3(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00))))$|^(?:0?[1-9]|1\d|2[0-8])(\/|-|\.)(?:(?:0?[1-9])|(?:1[0-2]))\4(?:(?:1[6-9]|[2-9]\d)?\d{2})$/`

## Tiempo

- Formato de hora HH: MM 12 horas, 0 inicial opcional – `/^(0?[1-9]|1[0-2]):[0-5][0-9]$/`

- Formato de hora HH: MM de 12 horas, 0 inicial opcional, Meridiems (AM / PM) – `/((1[0-2]|0?[1-9]):([0-5][0-9]) ?([AaPp][Mm]))/`

- Formato de hora HH: MM 24 horas, 0 inicial – `/^(0[0-9]|1[0-9]|2[0-3]):[0-5][0-9]$/`

- Formato de hora HH: MM 24 horas, 0 inicial opcional – `/^([0-9]|0[0-9]|1[0-9]|2[0-3]):[0-5][0-9]$/`

- Formato de hora HH: MM: SS 24 horas – `/(?:[01]\d|2[0123]):(?:[012345]\d):(?:[012345]\d)/`

## Etiquetas HTML

- Elementos con atributos – `/<\/?[\w\s]*>|<.+[\W]>/`

## Controladores de JavaScript

- Controlador JS en línea – `/\bon\w+=\S+(?=.*>)/`

- Controlador JS en línea con elemento – `/(?:<[^>]+\s)(on\S+)=["']?((?:.(?!["']?\s+(?:\S+)=|[>"']))+.)["']?/`

## Slug

- Slug – `/^[a-z0-9]+(?:-[a-z0-9]+)*$/`

## Coincidir duplicados en una cadena

- Buscar duplicados – `/(\b\w+\b)(?=.*\b\1\b)/`

## Números de teléfono

- Números de teléfono internacionales: con código / extensión de país opcional – `/^(?:(?:\(?(?:00|\+)([1-4]\d\d|[1-9]\d?)\)?)?[\-\.\ \\\/]?)?((?:\(?\d{1,}\)?[\-\.\ \\\/]?){0,})(?:[\-\.\ \\\/]?(?:#|ext\.?|extension|x)[\-\.\ \\\/]?(\d+))?$/`

## Ruta de archivo

- Ruta de archivo con nombre de archivo y extensión – `/((\/|\\|\/\/|https?:\\\\|https?:\/\/)[a-z0-9 _@\-^!#$%&+={}.\/\\\[\]]+)+\.[a-z]+$/`

- Ruta de archivo con nombre de archivo opcional, extensión – `/^(.+)/([^/]+)$/`

- Nombre de archivo con extensión de 3 caracteres – `/^[\w,\s-]+\.[A-Za-z]{3}$/`

----------

# jQuery Validation

Es una extensión de jQuery que sirve para la validación de formularios en el lado del cliente.

## Scripts requeridos

- jQuery: https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js

- jQuery Validate: https://cdn.jsdelivr.net/npm/jquery-validation@1.19.3/dist/jquery.validate.min.js

- Additional Methods: https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.19.3/additional-methods.min.js

## Referencia de reglas

| Regla | Devuelve FALSE | Ejemplo |
| -- | -- | -- |
| required | Hace el elemento requerido. | required: true |
| remote | Solicita un recurso para comprobar la validez del elemento. | remote: "check-email.php" |
| minlength | Hace que el elemento requiera una longitud mínima determinada. | minlength: 3 |
| maxlength | Hace que el elemento requiera una longitud máxima determinada. | maxlength: 4 |
| rangelength | Hace que el elemento requiera un rango de valores dado. | rangelength: [2, 6] |
| min | Hace que el elemento requiera un mínimo determinado. | min: 13 |
| max | Hace que el elemento requiera un máximo dado. | max: 23 |
| range | Hace que el elemento requiera un rango de valores dado. | range: [13, 23] |
| step | Hace que el elemento requiera un paso determinado. | step: 10 |
| email | Hace que el elemento requiera un correo electrónico válido | email: true |
| url | Hace que el elemento requiera una URL válida. | url: true |
| date | Hace que el elemento requiera una fecha. | date: true |
| dateISO | Hace que el elemento requiera una fecha ISO. | dateISO: true |
| number | Hace que el elemento requiera un número decimal. | number: true |
| digits | Hace que el elemento solo requiera dígitos. | digits: true |
| equalTo | Requiere que el elemento sea igual a otro. | equalTo: "#password" |
| accept | Hace que la carga de un archivo acepte solo tipos de mime especificados. | accept: "audio/*" |
| creditcard | Hace que el elemento requiera un número de tarjeta de crédito. | creditcard: true |
| extension | Hace que el elemento requiera una determinada extensión de archivo. | extension: "xls|csv" |
| phoneUS | Validar para un número de teléfono válido de EE. UU. | phoneUS: true |
| require_from_group | Garantiza que un determinado número de campos de un grupo esté completo. | require_from_group: [1, ".phone-group"] |

## Reglas personalizadas

~~~
jQuery.validator.addMethod("laxDate", function(value, element) {
  // allow any non-whitespace characters as the host part
  return this.optional( element ) || /([12]\d{3}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01]))/.test( value );
}, 'Please enter a valid date.');
~~~

## Eliminar espacios en blanco

~~~
rules: {
    nombre: {
        required: true,
        normalizer: function(value) {
            this.value = $.trim(value);
            return this.value;
            },
    },
},
~~~

## Llenar al menos uno de varios campos

~~~
$.validator.addClassRules("fillone", {
    require_from_group: [1, ".fillone"]
});
~~~

## Enviar controlador

~~~
$("#myform").validate({
    submitHandler: function (form) {
        form.submit();
    },
});
~~~

----------

# Ajax

## Estructura

~~~
$.ajax({
    type: "POST",
    contentType: "application/json; charset=utf-8",
    dataType: "dataType", /* json */
    url: "url", /* file.aspx/method */
    data: "data", /* JSON.stringify(parameters) */
    success: function (response) {
        /* alert("Success!"); */
    },
    error: function (response) {
        /* alert("Error!"); */
    },
});
~~~
