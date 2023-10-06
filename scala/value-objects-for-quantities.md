## Value objects for quantities and units of measure

As domain-driven-design suggests, it might be beneficial
to use value objects for objects where the identity is not relevant.
Typical use-cases are currencies, distances, etc.

For Scala, it turns out there is a library for such types, called [Squants](https://www.squants.com/).

Here is an example:

```scala
// without value objects
case class Generator(
  id: String,
  maxLoadKW: Double,
  rampRateKWph: Double,
  operatingCostPerMWh: Double,
  currency: String,
  maintenanceTimeHours: Double
)

val gen1 = Generator("Gen1", 5000, 7500, 75.4, "USD", 1.5)
val gen2 = Generator("Gen2", 100, 250, 2944.5, "JPY", 0.5)

// with Squants value objects
case class Generator(
  id: String,
  maxLoad: Power,
  rampRate: PowerRamp,
  operatingCost: Price[Energy],
  maintenanceTime: Time
)

val gen1 = Generator("Gen1", 5 MW, 7.5.MW / hour, 75.4.USD / MWh, 1.5 hours)
val gen2 = Generator("Gen2", 100 kW, 250 kWph, 2944.5.JPY / MWh, 30 minutes)
```

h/t @kiequoo 