# baud news ss 
This is a collection of json files automated by GitHub API in the backend.

## Get raw json data with get requests
- Tech news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/1_tech.json
- World news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/2_world.json
- Indian news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/3_india.json
- Asian news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/4_asia.json
- Europian news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/5_europe.json
- American news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/6_america.json
- African news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/7_africa.json
- Australian news : https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/8_australia.json

## Example code to fetch json data from above lists
```py
>>> import requests
>>> import json
>>> import pprint
>>> 
>>> res = requests.get("https://raw.githubusercontent.com/surdebmalya/baud-news-ss/main/3_india.json")
>>> res
<Response [200]>
>>> result = res.json()
>>> result.keys()
dict_keys(['articles', 'message', 'number_of_news', 'status', 'topic'])
>>> result['topic']
'india'
>>> result['status']
200
>>> result['message']
'Successful api call'
>>> result['number_of_news']
18
>>> result['articles'][0]
{'author': 'Express News Service', 'content': 'A SUPREME Court bench headed by Chief Justice of India S A Bobde Monday asked a state government employee, who is facing charges of raping a relative when she was a minor, if he intended to marry her… [+3429 chars]', 'description': '“Will you marry her?” the CJI asked while hearing a petition against an order of the Bombay High Court setting aside a sessions court order granting anticipatory bail to the accused.', 'publishedAt': '2021-03-01T23:12:00Z', 'source': {'id': None, 'name': 'The Indian Express'}, 'title': 'Man accused of raping relative when she was minor, CJI-led bench asks: will you marry her? - The Indian Express', 'url': 'https://indianexpress.com/article/india/man-accused-of-raping-relative-when-she-was-minor-cji-led-bench-asks-will-you-marry-her-7210283/', 'urlToImage': 'https://images.indianexpress.com/2021/02/supreme-court-10.jpg'}
>>> result['articles'][17]
{'author': 'Sporting News', 'content': '', 'description': "Pep Guardiola insists Bayern Munich are the best team in the world despite Manchester City's recent run of form.", 'publishedAt': '2021-03-01T05:13:31Z', 'source': {'id': None, 'name': 'Sporting News'}, 'title': "ISL 2020-21 Golden Boot: Roy Krishna, Igor Angulo lead the race to be India's topscorer - Goal India", 'url': 'https://www.sportingnews.com/ca/soccer', 'urlToImage': 'https://images.daznservices.com/di/library/sporting_news/a4/8/sportingnews_blid1xj976d41uqjx0jd6x52p.png'}
>>>
>>> pprint.pprint(result['articles'][0])
{'author': 'Express News Service',
 'content': 'A SUPREME Court bench headed by Chief Justice of India S A Bobde '
            'Monday asked a state government employee, who is facing charges '
            'of raping a relative when she was a minor, if he intended to '
            'marry her… [+3429 chars]',
 'description': '“Will you marry her?” the CJI asked while hearing a petition '
                'against an order of the Bombay High Court setting aside a '
                'sessions court order granting anticipatory bail to the '
                'accused.',
 'publishedAt': '2021-03-01T23:12:00Z',
 'source': {'id': None, 'name': 'The Indian Express'},
 'title': 'Man accused of raping relative when she was minor, CJI-led bench '
          'asks: will you marry her? - The Indian Express',
 'url': 'https://indianexpress.com/article/india/man-accused-of-raping-relative-when-she-was-minor-cji-led-bench-asks-will-you-marry-her-7210283/',
 'urlToImage': 'https://images.indianexpress.com/2021/02/supreme-court-10.jpg'}
>>> pprint.pprint(result['articles'][17])
{'author': 'Sporting News',
 'content': '',
 'description': 'Pep Guardiola insists Bayern Munich are the best team in the '
                "world despite Manchester City's recent run of form.",
 'publishedAt': '2021-03-01T05:13:31Z',
 'source': {'id': None, 'name': 'Sporting News'},
 'title': 'ISL 2020-21 Golden Boot: Roy Krishna, Igor Angulo lead the race to '
          "be India's topscorer - Goal India",
 'url': 'https://www.sportingnews.com/ca/soccer',
 'urlToImage': 'https://images.daznservices.com/di/library/sporting_news/a4/8/sportingnews_blid1xj976d41uqjx0jd6x52p.png'}
```
