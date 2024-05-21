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
