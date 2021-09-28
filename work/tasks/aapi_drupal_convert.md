# Converting AAPI product object format to Amazon Widget product format

### Amazon Widget format example
```
{
   "bundle":{
      "id":14198,
      "associateId":"tvm-trk-607-21",
      "name":"Samsung Galaxy Watch 3",
      "created_at":"2021-09-27 10:37:42",
      "updated_at":"2021-09-27 10:37:42",
      "mandant":{
         "id":7,
         "name":"TV Movie",
         "associateId":"tvm-content-21",
         "created_at":"2018-03-15 09:42:20",
         "updated_at":"2020-11-24 18:10:29",
         "active":"1",
         "css":"@font-face {\r\n  font-family: ###aws-iconfont###;\r\n  src: url(\"http:\/\/localhost:8080\/amazonwidget\/v1\/slider\/font\/eot\");\r\n  src: url(\"http:\/\/localhost:8080\/amazonwidget\/v1\/slider\/font\/eot\") format(\"eot\"), url(\"http:\/\/localhost:8080\/amazonwidget\/v1\/slider\/font\/woff\") format(\"woff\"), url(\"http:\/\/localhost:8080\/amazonwidget\/v1\/slider\/font\/ttf\") format(\"truetype\"); }\r\n\r\n.amazon-widget-service-icon:before {\r\n  font-family: ###aws-iconfont###;\r\n  speak: none;\r\n  font-style: normal;\r\n  font-weight: 400;\r\n  font-variant: normal;\r\n  text-transform: none;\r\n  \/*line-height: 1;*\/\r\n  background-color: transparent;\r\n  \/* Better Font Rendering =========== *\/\r\n  -webkit-font-smoothing: antialiased;\r\n  -moz-osx-font-smoothing: grayscale; }\r\n\r\n.amazon-widget-service-icon-arrow_slider:before {\r\n  content: ###\\E001###; }\r\n\r\n.amazon-widget-service-icon-arrow_slider_prev:before {\r\n  content: ###\\E002###; }\r\n\r\n.amazon-widget * {\r\n  text-decoration: none;\r\n  color: #000;\r\n  outline: 0; }\r\n\r\n.amazon-widget-box {\r\n  display: block;\r\n  text-align: center !important;\r\n  margin: 0 5px;\r\n  border: solid 1px rgba(0, 0, 0, 0.15); }\r\n\r\n.amazon-widget-product {\r\n  margin: 0 0 10px;\r\n  float: left;\r\n  text-align: center; }\r\n  .amazon-widget-product__title {\r\n    font-size: 15px;\r\n    font-weight: 900;\r\n    padding: 10px 5px;\r\n    text-align: center;\r\n    min-height: 52px; }\r\n  .amazon-widget-product__text {\r\n    font-size: 13px;\r\n    padding: 10px 5px;\r\n    text-align: center;\r\n    min-height: 52px; }\t\r\n  .amazon-widget-product__image {\r\n    float: none;\r\n    display: inline-block;\r\n    width: 180px;\r\n    height: 180px;\r\n    margin: 0 !important;\r\n    padding: 0;\r\n    overflow: hidden; }\r\n    .amazon-widget-product__image img {\r\n      width: 100%;\r\n      height: auto; }\r\n\r\n.amazon-widget-info {\r\n  float: none;\r\n  width: 100%; }\r\n  .amazon-widget-info * {\r\n    text-align: center !important; }\r\n  .amazon-widget-info__uvp, .amazon-widget-info__savings {\r\n    font-size: 13px;\r\n    line-height: 20px;\r\n    color: #9e9e9e;\r\n    margin-bottom: 5px; }\r\n    .amazon-widget-info__uvp span, .amazon-widget-info__savings span {\r\n      text-decoration: line-through; }\r\n  .amazon-widget-info__uvp span {\r\n    color: #9e9e9e; }\r\n  .amazon-widget-info__price {\r\n    font-weight: 900;\r\n    font-size: 15px;\r\n    margin-bottom: 35px;\r\n    line-height: 20px;\r\n    height: 20px;\r\n    overflow: hidden; }\r\n    .amazon-widget-info__price > span {\r\n      color: #e51200; }\r\n  .amazon-widget-info__savings {\r\n    height: 20px;\r\n    overflow: hidden;\r\n    margin-top: -30px; }\r\n    .amazon-widget-info__savings span {\r\n      text-decoration: none;\r\n      color: #e51200; }\r\n  .amazon-widget-info__button {\r\n    margin: 10px 0 20px; }\r\n    .amazon-widget-info__button span {\r\n      padding: 10px;\r\n      display: inline-block;\r\n      font-weight: 900;\r\n      text-transform: uppercase;\r\n      color: #fff;\r\n      font-size: 14px;\r\n      outline: 0 none; }\r\n      .amazon-widget-info__button span:before {\r\n        background: url(data:image\/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAUCAYAAACXtf2DAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyRpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw\/eHBhY2tldCBiZWdpbj0i77u\/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMC1jMDYxIDY0LjE0MDk0OSwgMjAxMC8xMi8wNy0xMDo1NzowMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENTNS4xIE1hY2ludG9zaCIgeG1wTU06SW5zdGFuY2VJRD0ieG1wLmlpZDpCNjMwOEFCQjIzMjMxMUU2OEM5QUUyMEE4RTVEOEM3NiIgeG1wTU06RG9jdW1lbnRJRD0ieG1wLmRpZDpCNjMwOEFCQzIzMjMxMUU2OEM5QUUyMEE4RTVEOEM3NiI+IDx4bXBNTTpEZXJpdmVkRnJvbSBzdFJlZjppbnN0YW5jZUlEPSJ4bXAuaWlkOkE3RTk1QkJFMjFBQTExRTY4QzlBRTIwQThFNUQ4Qzc2IiBzdFJlZjpkb2N1bWVudElEPSJ4bXAuZGlkOkI2MzA4QUJBMjMyMzExRTY4QzlBRTIwQThFNUQ4Qzc2Ii8+IDwvcmRmOkRlc2NyaXB0aW9uPiA8L3JkZjpSREY+IDwveDp4bXBtZXRhPiA8P3hwYWNrZXQgZW5kPSJyIj8+Tq6TVwAAAhhJREFUeNqU1U9IFkEYx3HX9zU1MzLTLAokUtG0P0hCKRJ2CC+GIqEIIuHJuze1k+f0IN1DiEiPooQoUujBg29JQdQphJcMgkTk9e\/6nfgpw7Kzb+\/AB3beefeZ3XlmnvV8389K04rRiQ5U4Cx28AWvMYtt591mggj3kPCj2yQuu2JEBb+BJStQCt+wjq3AJH3wwuJkRyxNPZp1fYiXqEIdhgPL8gAXwoLEHcHNxElM68YfeGWNv0cP7qtf5IrlmuAIH8W0GEpxW\/c0KPmnqXQtQzzNDspHI1rxEDU4n5VBi5rgHAYwhEL99htLuq\/uvyaL2EUdgZ0yjxbkohar1thblITFcb3BRbRZ\/Q2MY8HaBDFrfE95C90tYa0AlVbfLM1Pq38X5Va\/DLmZTGCeJmX1TYl4YgXv19Y8aS14FJpTx\/oXYDSQgyTmdJrD2hSKMykVdyLq0Dv04JP6y3iMeDCOqR\/mmK84lq9albRBa5xUomewiXadk0kkcBXduKXrhJngKRe9eIOpkInyVC7MhLvYwr7GciSlvOXpMN7EFbw4We8mLGp9R1CRpoy78tauPI0q5oqnD062as0zDOKa9v4HrOE7funpTWU9o7NyXfWpSbvrDyZ0Zsb+1bLAU5gkXUIXZrGjJB5hT98EYxcHGjP\/WcBzlCIHMbSZa8\/xyfQCFbRGT1uksb86eF\/xWW93EKiq5n\/+sQADADsXiuXHTAk1AAAAAElFTkSuQmCC) no-repeat;\r\n        background-size: 20px 16px;\r\n        content: ######;\r\n        width: 20px;\r\n        height: 16px;\r\n        float: left;\r\n        margin-right: 10px; }\r\n\r\n.amazon-sprite {\r\n  background-image: url(\"https:\/\/images-na.ssl-images-amazon.com\/images\/G\/01\/AUIClients\/AmazonUIBaseCSS-sprite_2x-9d768db982f81e1fde71be6e1f86b818ea0ecfcf._V2_.png\");\r\n  -webkit-background-size: 400px 650px;\r\n  -moz-background-size: 400px 650px;\r\n  -o-background-size: 400px 650px;\r\n  background-size: 400px 650px;\r\n  background-repeat-x: no-repeat;\r\n  background-repeat-y: no-repeat;\r\n  display: inline-block; }\r\n  .amazon-sprite--prime {\r\n    width: 52px;\r\n    height: 16px;\r\n    background-position: -5px -489px;\r\n    vertical-align: baseline; }\r\n\r\n.amazon-widget-info__button span {\r\n  background-color: #e51200; }\r\n"
      },
      "products":[
         {
            "id":15987,
            "bundle_id":"14198",
            "sortkey":"0",
            "title":"Samsung Galaxy Watch3, runde Bluetooth Smartwatch f\u00fcr Android, drehbare L\u00fcnette, 4G, Fitnessuhr, Fitness-Tracker, gro\u00dfes Display, 45 mm, Titanium, inkl. 36 Monate Herstellergarantie [Exkl. bei Amazon]",
            "affiliateId":null,
            "producttext":"",
            "asin":"B08CRXNNDB",
            "created_at":"2021-09-27 10:37:49",
            "updated_at":"2021-09-27 10:37:52",
            "image":"https:\/\/m.media-amazon.com\/images\/I\/31Ke6e68v8L._SL500_.jpg",
            "imageWidth":"500",
            "imageHeight":"333",
            "isPrime":"1",
            "url":"https:\/\/www.amazon.de\/dp\/B08CRXNNDB?tag=tvm-trk-607-21&linkCode=ogi&th=1&psc=1",
            "price":"339,99\u00a0\u20ac",
            "listPrice":"439,99\u00a0\u20ac",
            "savingtotal":"100,00\u00a0\u20ac (23%)",
            "savingPercentage":"23"
         }
      ]
   }
}
```

### AAPI format example
```
{
  "asin": "B08CRXNNDB",
  "affiliateUrl": "https://www.amazon.de/dp/B08CRXNNDB?tag=tvm-trk-607-21&linkCode=ogi&th=1&psc=1",
  "image": {
    "url": "https://m.media-amazon.com/images/I/31Ke6e68v8L._SL500_.jpg",
    "width": 500,
    "height": 333
  },
  "title": "Samsung Galaxy Watch3, runde Bluetooth Smartwatch für Android, drehbare Lünette, 4G, Fitnessuhr, Fitness-Tracker, großes Display, 45 mm, Titanium, inkl. 36 Monate Herstellergarantie [Exkl. bei Amazon]",
  "description": "<p>Fitness-Daten im Blick behalten: Die Samsung Galaxy Watch3 kann Sie dabei unterstützen, die ideale Balance zwischen Alltag und Workout finden – mit vielen Fitnesstracker-Funktionen, über 120 Workout-Programmen auf der Smartwatch und der Schlafanalyse.</p><p>Präzise Steuerung mit drehbarer Lünette: Die neue Samsung Smartwatch mit drehbarer Lünette ist leicht zu bedienen und kann problemlos mit einer Vielzahl von Galaxy-Geräten und Geräten anderer Hersteller verbunden werden.</p><p>Die passende 4G Smartwatch für Ihren Lifestyle: Die Galaxy Watch3 mit smartem Fitness-Tracker ist in den Größen 45 mm und 41 mm sowie in den Premium-Farbvarianten Schwarz, Silber und Bronze erhältlich. Abmessungen (HxBxT): 46,2 x 45,0 x 11,1 mm</p><p>Die Bluetooth Smartwatch im klassischen Premium-Design: Die drehbare Lünette der neuen Fitnessuhr rahmt das große Display dezent ein und bietet dank ihres leichten, schlanken Designs hohen Tragekomfort.</p><p>Die robuste Galaxy Smartwatch verfügt über eine IP68-Zertifizierung und ist damit vor Wasser und Staub geschützt. Außerdem ist die Smartwatch für Android bis zu 5 ATM wassergeschützt.</p><p>Welche komponenten sind im lieferumfang des produkts enthaltenen: Galaxy Watch3, BT (Titanium 45 mm), Wireless Charger, Quick Start Guide</p>",
  "offerCount": 1,
  "lowestNewPrice": 33999,
  "listPrice": 43999,
  "availability": "Auf Lager.",
  "isEligibleForPrime": true,
  "saving": 10000,
  "awsTag": "tvm-trk-607-21"
}
```

### Conversion code (pseudo-js)

``` javascript
// these properties should be set from widget data
// Bundle.products[0].id
// Bundle.products[0].bundle_id
// Bundle.products[0].sortkey
// Bundle.products[0].created_at
// Bundle.products[0].updated_at

// these properties can be converted from the AAPI object
Bundle.products[0].asin = AAPI.asin,
Bundle.products[0].title = AAPI.title,
Bundle.products[0].affiliateId = AAPI.awsTag, // I'm not sure about this...
Bundle.products[0].image = AAPI.image.url,
Bundle.products[0].imageWidth = AAPI.image.width,
Bundle.products[0].imageHeight = AAPI.image.height,
Bundle.products[0].prime = AAPI.image.isPrimeEligible ? 1 : 0,
Bundle.products[0].producttext = AAPI.image.description,
const listPrice = AAPI.image.listPrice / 100
const price = AAPI.image.lowestNewPrice / 100
Bundle.products[0].price = price,
Bundle.products[0].listPrice = listPrice,
const saving = ((listPrice - price) / price ) / * 100
Bundle.products[0].savingtotal = `${AAPI.saving / 100} (${saving}%)`,
Bundle.products[0].savingPercentage = saving
```
