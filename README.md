# EmpresaTurismo
TP Final de la materia Programaciòn Orientada a Objetos


# Sistema de Gestión de Viajes

## Descripción

Este proyecto es un sistema de gestión de viajes desarrollado en Smalltalk. Permite administrar clientes, viajes y contratos, incluyendo la reprogramación y cancelación de los mismos.

## Características Principales

- Registro y gestión de clientes.
- Creación y administración de contratos de viaje.
- Gestión de viajes organizados y especiales.
- Control de excursiones opcionales.
- Reprogramación y cancelación de contratos.
- Manejo de millas para viajeros frecuentes.

## Estructura del Proyecto

### Clases Principales

- **EmpresaTurismo**: Administra clientes, viajes y contratos.
- **Cliente**: Representa a un cliente con sus contratos.
- **ViajeroFrecuente**: Subclase de Cliente con sistema de millas.
- **Contrato**: Representa un contrato de viaje.
- **ContratoFlexible**: Subclase de Contrato con posibilidad de reprogramación.
- **Viaje**: Representa un viaje general.
- **Especial**: Subclase de Viaje con fecha de salida y regreso.
- **Organizado**: Subclase de Viaje con etapas y excursiones.
- **Jornada**: Representa un día dentro de un viaje organizado.
- **Etapa**: Representa una parte de un viaje organizado.
- **ExcursionOpcional**: Excursión disponible dentro de un viaje organizado.

## Instalación y Ejecución

1. Instalar Smalltalk (Pharo recomendado).
2. Clonar el repositorio:
   ```sh
   git clone https://github.com/lopezernesto/EmpresaTurismo
   ```
3. Cargar el código en el entorno de Smalltalk.
4. Crear una instancia de `EmpresaTurismo` para iniciar:
   ```smalltalk
   empresa := EmpresaTurismo crear.
   Contrato inicializarNroContrato .
   ```

## Uso Básico

### Agregar un Cliente

```smalltalk
cliente := Cliente crear: '12345678' ape: 'Perez' city: 'Buenos Aires' correo: 'perez@mail.com' tel: '123456789' pref: 'Playa'.
empresa agregarCliente: cliente.
```

### Crear un Viaje Especial

```smalltalk
viaje := Especial crear: 'Mar del Plata' f_salida: (Date today) ciudad: 'Mar del Plata' f_vuelta: (Date today addDays: 5) imp: 100 costo: 500 cantPersonas: 30.
empresa agregarViaje: viaje.
```

### Crear un Contrato

```smalltalk
empresa crearContrato: '12345678' viaje: 'Mar del Plata' cant: 2 f: (Date today).
```

### Cancelar un Contrato

```smalltalk
empresa cancelacionContrato: 1.
```

### Reprogramar un Contrato

```smalltalk
empresa reprogramacionContrato: 1 fecha: (Date today addDays: 10).
```
