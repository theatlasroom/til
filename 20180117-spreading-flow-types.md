```
type Engine = {
  size: string,
  model: string,
}

type Specs = {
  price: number,
  wheels: number,
  doors: number,
}

type Availability = {
  isAvailable: boolean,
}

type Car = {
  ...Availability, // optional spreaded properties
  ...$Exact<Engine>, // require spreaded properties
  ...$Exact<Specs>, // require spreaded propertie
}

function newCar(car: Car) {
	console.log(car)
}

const lambo = {
  price: 100000,
  wheels: 4,
  size: 'BADASS',
  doors: 2,
  model: 'Miura',
}

const maserati = {
  price: 100000,
  wheels: 4,
  size: 'BADASS',
  doors: 2,
  model: '350 S',
  isAvailable: true,
}

newCar(lambo)
newCar(maserati)
```
