---
id: release-8.9.14
title: 'Drupal 8.9.14'
path: /8/releases/8.9.14
core: 8
metatags:
  title: 'Drupal 8.9.14: Список изменений'
  description: 'Список изменений Drupal 8.9.14.'
---

**Дата релиза**: 3 марта 2021

## Editor

- [#2857444](https://www.drupal.org/project/drupal/issues/2857444) Улучшено отслеживание файлов в полях отличных от `text`, `text_long` и `text_with_summary`. Теперь данные файлы отслеживаются для всех полей что расширяют `TextItemBase`.

## Serialization

- [#3054510](https://www.drupal.org/project/drupal/issues/3054510) Исправлена документация для `NormalizerBase::supportsDenormalization()`.

## Views

- [#2969107](https://www.drupal.org/project/drupal/issues/2969107) Аргументы для даты больше не возвращают HTTP 500 при некорректном формате.

## Прочие изменения

- [#3192231](https://www.drupal.org/project/drupal/issues/3192231) Исправлена работа теста `UnroutedUrlTest` на dev версиях PHP.
- [#3199205](https://www.drupal.org/project/drupal/issues/3199205) `Archive_Tar` обновлён до 1.4.13.