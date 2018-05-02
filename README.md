## Learning Competencies

* Mampu menuliskan code dengan mendefinisikan method, parameter dan return value yang akurat
* Mampu mengenali karakteristik dari sebuah code yang bagus dan mengikuti Best Practices dan mengimplementasikannya ke dalam code.

## Releases

### Release 0 : Use named arguments

Coba lihat constructor dari class `House` di skeleton code. Banyak parameter-nya.

```javascript
class House {
  constructor(address, square_feet, num_bedrooms, num_baths, cost, down_payment, sold, has_tenants) {
  // ...
  }
  // ...
}
```

Tugas kamu di *release* ini adalah melakukan refactor method tersebut supaya menggunakan named arguments.

### Release 1 : Be wary of booleans

Apa yang terjadi jika kita mengirimkan boolean atau `null` ke parameter yang bukan boolean? Lihat contoh berikut ini:

```javascript
'use strict'

class Car {
  start_car(options) {
    if (options && options['headlights'])
      this.headlights = options['headlights']
    else
      this.headlights = true

    if (options && options['gear'])
      this.gear = options['gear']
    else
      this.gear = 1
  }
}

var herbie = new Car

// When we start the car, the headlights should be on by default
herbie.start_car()
console.log(herbie.headlights) // true

// But what happens when we want to start without headlights?
herbie.start_car({headlights: false})
console.log(herbie.headlights) // true ...KOK BISA?!
```

Untuk menghindari hal ini  kita bisa menggunakan method `hasOwnProperty()` pada pengecek kondisi. Silakan baca artikel [JavaScript hasOwnProperty() Method](http://brianflove.com/2013/09/05/javascripts-hasownproperty-method) untuk mengetahui lebih lanjut tentang method ini.

Kemudian refactor code kamu (bisa yang `house.js` atau eksperimen baru di `car.js`) sehingga kesalahan di baris terakhir code di atas dapat dihindari.
