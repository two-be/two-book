---
tags:
  - JavaScript
---

## Flatten an array of arrays
```javascript
let flattened = [[0, 1], [2, 3], [4]].reduce((x, y) => x.concat(y))

// flattened is [0, 1, 2, 3, 4]
```

## Locale Date String
```javascript
let date = new Date(2020, 1, 29)

date.toLocaleDateString("th-TH", {
    year: "numeric",
    month: "long",
    day: "numeric"
})

// 29 กุมภาพันธ์ 2563
```

## Sort an array of dates
```javascript
let dates = [
  new Date(2022, 1, 2),
  new Date(2022, 0, 2),
];

dates.sort((x, y) => x - y)

// [Sun Jan 02 2022 00:00:00 GMT+0700 (Indochina Time), Wed Feb 02 2022 00:00:00 GMT+0700 (Indochina Time) ]
```

## Suffle an array
```javascript
let shuffled = [0, 1, 2, 3, 4].sort(() => 0.5 - Math.random())

// shuffled may be [2, 3, 4, 1, 0]
```