# Сбор данных о погоде по всему миру, используя сайт Гидрометцентр России (meteoinfo.ru)

# Цель проекта
Собрать данные о погоде из всех стран мира, их регионов, если таковые существуют, а также городов для дальнейшего использования в своих целях, в различных приложениях или для анализа данных. Также, в цели проекта входит предложение о способе хранения данных (то есть, модель данных)

# Собранные данные
В сбор данных входят такие данные как:
- Страны
- Регионы, которые находятся в этой стране (если есть)
- Города
- Дата
- Дневное/ночное измерение погодных условий в конкретном городе
- Температура масимальная в конкретном городе
- Осадки, их вероятность в конкретном городе
- Ветер, м/с в конкретном городе
- Давление, мм. рт.ст в конкретном городе

# Как программа вернёт данные
по окончании сбора данных программа вернёт данные в JSON формате.
Пример:
```
{
  'mainPage': 'https://meteoinfo.ru/forecasts/',
  'countries': {
    'russia': {
      'name': 'Россия',
      'url': 'https://meteoinfo.ru/forecasts/russia'
      'response': '<Response [200]>',
      'has_regions': True
      }
    },
  'regions': {
      'republic-bashkortostan': {
        'name': 'Башкорстостан',
        'url': 'https://meteoinfo.ru/forecasts/russia/republic-bashkortostan',
        'response': '<Response [200]>',
        'has_regions': True,
        'country': {
            'name': 'russia',
            'url': 'https://meteoinfo.ru/forecasts/russia',
          },
      },
    },
  'cities': {
      'Ufa': {
          'name': 'уфа',
          'url': 'https://meteoinfo.ru/forecasts/russia/republic-bashkortostan/Ufa',
          'response': '<Response [200]>',
          'has_regions': True,
          'region': {
              'name': 'republic-bashkortostan',
              'url': 'https://meteoinfo.ru/forecasts/russia/republic-bashkortostan',
          },
          'country': {
            'name': 'russia',
            'url': 'https://meteoinfo.ru/forecasts/russia',
          },
          'information': {
              '14 сентября': {
                  'temperature': 29,
                  'precipitation': 95,
                  'wind': 2,
                  'pressure': 761
                },
              '15 сентября': {
                  'temperature': 29,
                  'precipitation': 95,
                  'wind': 2,
                  'pressure': 761
                },
          }
      },
    },
}
```

# Модель данных, предлагаемая для этого проекта

