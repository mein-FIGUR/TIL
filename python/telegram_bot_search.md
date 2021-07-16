### 텔레그램 봇으로 상품 검색하기











```python
import requests

#기본 설정
TOKEN = '1883623049:AAFvgetUZYEM6Zi4hb_inUH_hB7OaEfjMcw'
APP_URL = f'https://api.telegram.org/bot{TOKEN}'

#chat_id 가져오기
#https://api.telegram.org/bot1883623049:AAFvgetUZYEM6Zi4hb_inUH_hB7OaEfjMcw/getUpdates

UPDATES_URL = f'{APP_URL}/getUpdates'
response = requests.get(UPDATES_URL).json()

chat_id = response.get("result")[0].get('message').get('chat').get('id')

# 검색하고자 하는 단어
need_to_search = response.get("result")[-1].get('message').get('text')

print(need_to_search)


##### 네이버 서치

# naver 요청 보낼 때 필요한 것들
naver_client_id = 'kQkGdOK3n3bqSWM_0knb'
naver_client_secret = 'Qb9M_BvbKW'
URL = 'https://openapi.naver.com/v1/search/shop.json?query='

headers = {
    'X-Naver-Client-Id': naver_client_id,
    'X-Naver-Client-Secret': naver_client_secret
}

query = need_to_search

product = requests.get(URL+query, headers=headers).json()['items'][0]
#print(product)
product_name = product['title']
#print(product_name)
product_price = product['lprice']
#print(product_price)
product_link = product['link']
#print(product_link)

message = f'{product_name}\n{product_price}\n{product_link}'
print(message)


text = message

#https://api.telegram.org/bot1883623049:AAFvgetUZYEM6Zi4hb_inUH_hB7OaEfjMcw/sendMessage?chat_id=1799306322&text=%EB%B3%B4%EB%82%B4%EC%A7%80%EB%82%98%EC%9A%94?
message_url = f'{APP_URL}/sendMessage?chat_id={chat_id}&text={text}'

requests.get(message_url)
```

