# DPO_CL_Project
This repository contains code and supporting material for my CL project involving corpora cleansing and preparation for MT training. 

# Резюме
С появлением на рынке коммерческих вариантов API для нейронного машинного перевода (МП) и их широким распространением все больше поставщиков услуг перевода и клиентов заинтересованы в применении технологий МП для решения стоящих перед ними задач перевода. МП высоко зарекомендовал себя во множестве областей, позволяя автоматизировать и существенно ускорить перевод контента, объемы которого растут экспоненциально. Зачастую моделей общей тематики (универсальных моделей) недостаточно для качественного перевода сложных текстов, кроме того, у отдельных клиентов могут существовать особые требования с точки зрения терминологии и стиля.</br>

<b>Повышение качества МП в отдельных тематиках за счет тренировки специализированных (кастомных) моделей на параллельных корпусах высокого качества является интересным и востребованным направлением.</b>

## Задача № 1
Важнейшим этапом подготовки параллельного корпуса к тренировке модели является его фильтрация и валидация. Один из значимых этапов очистки данных предполагает удаление из корпуса дубликатов, однако дубликатами могут выступать не только полностью идентичные единицы. Возникает необходимость удаления дубликатов по ряду критериев, таких как, например: </br>
<li>	даты</li>
<li>	номера телефонов в разных форматах</li>
<li>	наличие ссылок</li>
<li>	значения полей</li>
<li>	опечатки</li>
<li>	лишние символы (лишние пробелы, мягкие переносы)</li>

Надо отметить, что этап удаления дубликатов является только одной из задач. Дополнительные возможные задачи будут рассмотрены далее. 

### Данные
В данном проекте данные в виде параллельных корпусов уже накоплены в формате .tmx, который является exchange-форматом так называемой памяти переводов — Translation Memory (TM). Это xml-нотация для представления параллельных корпусов, в том числе метаданных, которая имеет понятную структуру и которая доступна для анализа и парсинга. </br>

Такие корпуса накапливались годами в процессе перевода и имеют размерность от 10 000 до 60 000 сегментов, достаточную для тренировки специализированных моделей.

### Подход к разработке проекта
Разработка проекта включает в себя несколько этапов:
<li> Изучение и анализ структуры xml-файлов, изучение The ElementTree XML API
  
