HU 002: Modificación de datos personales
Como cliente bancario, quiero poder modificar mi dirección registrada en caso de mudanza.
Criterios de Aceptación:
● Dado que ingreso la nueva dirección y mi código de seguridad, el sistema actualiza la
información en mi perfil.
● Debo recibir una notificación de confirmación.



Feature: Modificación de datos personales de cliente bancario

  Scenario: Modificación exitosa de dirección
    Given soy un cliente bancario
    And estoy autenticado en mi perfil
    When ingreso la nueva dirección "Mi Nueva Dirección" y mi código de seguridad
    Then el sistema actualiza la información en mi perfil
    And recibo una notificación de confirmación

  Scenario: Fallo en la modificación de dirección
    Given soy un cliente bancario
    And estoy autenticado en mi perfil
    When ingreso la nueva dirección "Mi Nueva Dirección" y un código de seguridad incorrecto
    Then el sistema no actualiza la información en mi perfil
    And no recibo una notificación de confirmación








    

HU 003: Solicitud de tarjeta de crédito
Como cliente bancario, quiero poder solicitar una tarjeta de crédito en línea para aprovechar los
beneficios y límites de crédito.
Criterios de Aceptación:
● Dado que ingreso la solicitud de tarjeta de crédito con la información requerida, recibo
una confirmación de que la solicitud ha sido recibida.
● Si la solicitud es aprobada, recibo una notificación con los detalles de la tarjeta y sus
beneficios.
● Si la solicitud es rechazada, recibo una notificación con el motivo del rechazo.





Feature: Solicitud de tarjeta de crédito de Como cliente bancario

  Scenario: Solicitud de tarjeta de crédito exitosa
    Given soy un cliente bancario
    When ingreso la solicitud de tarjeta de crédito con la información requerida
    Then recibo una confirmación de que la solicitud ha sido recibida

  Scenario: Aprobación de solicitud de tarjeta de crédito
    Given soy un cliente bancario
    When ingreso la solicitud de tarjeta de crédito con la información requerida
    And la solicitud es aprobada
    Then recibo una notificación con los detalles de la tarjeta y sus beneficios

  Scenario: Rechazo de solicitud de tarjeta de crédito
    Given soy un cliente bancario
    When ingreso la solicitud de tarjeta de crédito con la información requerida
    And la solicitud es rechazada
    Then recibo una notificación con el motivo del rechazo
