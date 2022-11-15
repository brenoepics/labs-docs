---
title: "Getting basic values"
page_id: "getting-basic-values"
order: 1
updated: 2022-11-08
warning: false
---

### Topics in this section

- [Getting a top level field](#getting-a-top-level-field)
- [Getting a nested field](#getting-a-nested-field)
- [Getting an entire object](#getting-an-entire-object)
- [Selecting a specific index in an array](#selecting-a-specific-index-in-an-array)
- [Selecting a whole array](#selecting-a-whole-array)
- [Return just one field of every object in an array](#return-just-one-field-of-every-object-in-an-array)
- [Returning fields that contain special characters in the key name](#returning-fields-that-contain-special-characters-in-the-key-name)

*Imagine you have the following JSON data returned by an endpoint:*

``` json
{
    "name": "John Smith",
    "address": {
        "street": "123 Park Avenue",
        "city": "Atlanta",
        "state": "GA",
        "zip": "12345"
    },
    "phones": [
        {
            "type": "Home",
            "number": "123-456-7890"
        },
        {
            "type": "Cell",
            "number": "098-765-4321"
        }
    ],
    "display name": "myuser123"
}
```

---

### Getting a top level field

#### FQL

``` javascript
name
```

<br>

#### Result

``` json
"John Smith"
```

---

### Getting a nested field

#### FQL

``` javascript
address.city
```

<br>

#### Result

``` json
"Atlanta"
```

---

### Getting an entire object

#### FQL

``` javascript
address
```

<br>

#### Result

``` json
{
    "street": "123 Park Avenue",
    "city": "Atlanta",
    "state": "GA",
    "zip": "12345"
}
```

---

### Selecting a specific index in an array

#### FQL

``` javascript
phones[0].number
```

<br>

#### Result

``` json
"123-456-7890"
```

---

### Selecting a whole array

#### FQL

``` javascript
phones
```

<br>

#### Result

``` json
[
    {
        "type": "Home",
        "number": "123-456-7890"
    },
    {
        "type": "Cell",
        "number": "098-765-4321"
    }
]
```

---

### Return just one field of every object in an array

#### FQL

``` javascript
phones.number
```

<br>

#### Result

``` json
["123-456-7890","098-765-4321"]
```

---

### Returning fields that contain special characters in the key name

#### FQL

``` javascript
`display name`
```

<br>

#### Result

``` json
"myuser123"
```

---