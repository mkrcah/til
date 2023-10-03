## Filter and mapValues within one function

I needed to convert `Map[String, Option[Int]]` to `Map[String, String]` for the values
where the option is defined. Initially, I used a combination of `filter` and `mapValues`:

```scala
val queryParams = Map(
  "limit" -> Some(10),
  "offset" -> None
).filter(_._2.isDefined).mapValues(_.get.toString)

println(queryParams) // Map("limit" -> "10") 
```

However, the `_.get` is fragile, as it depends on the `isDefined` used before. If only there would
be a function which would take a partial function pattern-matching on `Option`.

It turns out, there is, and it's called `collect`:

```scala 
val queryParams = Map(
  "limit" -> Some(10),
  "offset" -> None
).collect {
  case (paramName, Some(paramValue)) => (paramName, paramValue.toString)
}
println(queryParams) // Map("limit" -> "10")
```