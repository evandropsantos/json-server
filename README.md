# json server
☕️ É um pacote NPM que se propõe a criação de fakes Rest APIscom zero coding
## GET
*Filtra por item*
- http://localhost:3000/products/1

*Filtra por dados*
- http://localhost:3000/products?category=electronics
- http://localhost:3000/products?category=electronics&discount.type=shipping

*Ordenação*
- http://localhost:3000/products?_sort=price
- http://localhost:3000/products?_sort=price&_order=desc
- http://localhost:3000/products?_sort=price,category&_order=desc,asc <!--Multipla ordenação - ordena a categoria com price 3000 por ordem crescente-->

*Paginação*
- http://localhost:3000/products?_page=1&_limit=2

<!--No inspector - aba network, cabeçalhos - link mostra informações de response (next, last, total) -->

*Operadores*
- http://localhost:3000/products?price_gte=2000&price_lte=6000 <!--Range -->
- http://localhost:3000/products?id_ne=1 <!--Not equal -->
- http://localhost:3000/products?category_like=^f <!--expressão regular -->

*Pesquisa de texto completo*
- http://localhost:3000/products?q=in

*Relacionamento*
- http://localhost:3000/products?_embed=reviews
- http://localhost:3000/products/1?_embed=reviews
- http://localhost:3000/reviews?_expand=product

## POST Request
```
URL: http://localhost:3000/products
Body:
{
  "id": 11,
  "title": "Product 11",
  "category": "electronics",
  "price": 4000,
  "description": "This is description about product 11"
}
```

## PUT Request
```
URL: http://localhost:3000/products/11
Body:
{
  "id": 11,
  "title": "Product 11",
  "category": "furniture",
  "price": 4000,
  "description": "This is description about product 11"
}
```

## PATCH Request
```
URL: http://localhost:3000/products/11
Body:
{
  "price": 8000,
}
```

## DELETE Request
```
URL: http://localhost:3000/products/11
Body: Vazio
```

### Configurações
Porta: --port 4000
Routes: --routes routes.json 
ex.:
```
"/products/:category": "/products?category=:category"
```
*Possibilita a pesquisa por categoria na URL http://localhost:4000/products/electronics

### Gerar Dados Randomicos
[data.js](data.js)
