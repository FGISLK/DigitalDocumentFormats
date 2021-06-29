# Форматы электронных документов

## Коды услуг
* [forestDeclaration](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/forestDeclaration) - лесная декларация;
* [forestUsageReport](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/forestUsageReport) - отчет об использовании лесов;
* [forestReproduction](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/forestReproduction) - отчет о воспроизводстве лесов; 
* [forestFireSecurity](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/forestFireSecurity) - отчет об охране лесов от пожаров;
* [forestProtection](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/forestProtection) - отчет о защите лесов;

## Прочие форматы
* [сommonTypes](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/commonTypes) - общие типы для всех форматов;
* [catalogs](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/catalogs) - справочники;

## Прочие ресурсы
[catalogsList](https://github.com/FGISLK/DigitalDocumentFormats/tree/main/catalogsList) - перечень справочников, используемых при обмене;

## Описание пакета обмена
Электронный документ обмена состоит из набора файлов, упакованных в один ZIP - архив (далее Пакет). Пример пакета смотри по [ссылке](https://github.com/FGISLK/DigitalDocumentFormats/blob/main/forestDeclaration/3.0/forestDeclaration-000000004_00037.zip?raw=true).

Пакет содержит:
- В корне пакета:
    - Одиночный XML-файл заявления, созданный по утвержденной схеме передаваемой услуги;
    - Файл открепленной подписи XML-файла заявления сформированной по алгоритму ГОСТ 34.10-2012, 256 бит.
    - Каталог "files":
        - электронные образы документов, прикрепленных к заявлениям;
        - файл визуализации заявления;

Имя Пакета должно иметь следующий вид: **<[Код услуги](#%D0%BA%D0%BE%D0%B4%D1%8B-%D1%83%D1%81%D0%BB%D1%83%D0%B3)>-<Идентификатор документа в информационной базе поставщика>.zip**.

Имя XML-файла заявления должно иметь следующий вид: **<[Код услуги](#%D0%BA%D0%BE%D0%B4%D1%8B-%D1%83%D1%81%D0%BB%D1%83%D0%B3)>.xml**.

Имя файла открепленной электронной подписи XML-файла заявления, должно иметь вид: **<имя подписываемого файла>[.p7s;.sig]**.

Наименования имён файлов в каталоге "files" могут состоять из букв латинского алфавита, цифр и символов - _. Длина наименования имен файлов должна быть не более 200 символов.
Данные о электронных документах в каталоге "files" описаны в XML-файле заявления в тэге **attachments**.

Открепленные электронные подписи файлов из данного каталога в формате base64 записываются в тэг **signature**.

## Проектные решения
### Описание типа reference
* Тип **reference** является родителем для всех типов данных, используемых при описании справочников (далее НСИ).
* При описании элемента НСИ, атрибут **id** может быть не обязательным.
