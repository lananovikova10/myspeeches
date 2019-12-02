# Дополнительные материалы

## Слайды

Ссылка: 

## Пример конфигурации Redoc в Sphinx

``` python
extensions = [
    'sphinxcontrib.redoc',
]

redoc = [
    {
        'name': html_short_title,
        'page': 'docs/api',
        'spec': 'openapi.json',
        'embed': True,
    },
]
redoc_uri = 'https://cdn.jsdelivr.net/npm/redoc@next/bundles/redoc.standalone.js'
```

## Список упомянутых инструментов

- Sphinx SSG (http://www.sphinx-doc.org/en/master/)
- Redoc API doc visualizer (https://github.com/Redocly/redoc)
- Спецификация openapi 3 (https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md)
- Chai OpenAPI Response Validator (https://github.com/RuntimeTools/chai-openapi-response-validator)

## Гайдлайн к описанию поля

The requirements for the descriptions are below.

API field descriptions shouldn’t be longer than 160 symbols with spaces and must contain:

- Short business sense and behavior description not repeating the field name. (Answers questions: What is it and what it does when valid. How do we use it).
- Field limits, what makes it valid/invalid, for example, max length, accuracy, rounding, units (USD, centimeters, etc.). Any conditional statements when it present and when it’s not.

Can contain:

- An example value.
- The default value or behaviors if so, what system will do if no value will be passed.
- For a string, you can describe the syntax, for example, b64 or [A-a0-9] or URL. For number - range of values.

For example, “Segment id, digits only, can not be changed once set, unique across all segments” or “Direct publisher. Required only if demand_type==’direct’. In other cases must be null and present in request even for network and rtb”.

Do not start the description line with special symbols or escape them using because description supports CommonMark notation.

