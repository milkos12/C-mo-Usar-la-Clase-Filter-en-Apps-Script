# Uso de la Clase `Filter` en Apps Script

![Google Apps Script](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_Apps_Script.svg/1024px-Google_Apps_Script.svg.png)

## Descripción

Este proyecto demuestra cómo utilizar la clase `Filter` de Google Apps Script para aplicar filtros a columnas en Google Sheets de manera automatizada. El código proporciona una guía paso a paso para seleccionar un rango de datos, definir criterios de filtrado y aplicar estos filtros a una hoja de cálculo.

## Características

- **Selección de Rango de Datos**: Cómo seleccionar un rango específico en tu hoja de cálculo.
- **Definición de Criterios de Filtrado**: Cómo crear criterios personalizados para el filtrado de datos.
- **Aplicación del Filtro**: Cómo aplicar los criterios definidos a la columna deseada.

## Uso

### Paso 1: Configuración Inicial

1. Abre Google Sheets y crea una nueva hoja de cálculo.
2. Ve a `Extensiones` > `Apps Script`.

### Paso 2: Copia y Pega el Código

```javascript
function main() {
  const book = SpreadsheetApp.openById('1oFCfX-r0uRcv4uNGBsZEnuy7uFKgeTIzZnDutICovKs'); // ID DE TU SPREADSHEET
  const sheet = book.getSheetByName('report'); // NOMBRE DE LA HOJA DONDE ESTA LA COLUMNA QUE VAS A FILTRAR
  filter(sheet);
}

function filter(sheet) {
  const filterSheet = sheet.getFilter();
  let criteriaFilter = SpreadsheetApp.newFilterCriteria()
                                      .setHiddenValues(['no']) // VALOR QUE VAS HA ESCONDER O VALORES POR EJEMPLO ['no','si']
                                      .build();

  filterSheet.setColumnFilterCriteria(5, criteriaFilter);
  console.log('hello!')
}

