# IEEE 754 floating point math

I initially noticed a strange occurence in the browser when doing maths in
JavaScript.

The math is simple:

```
let num =0
num+=8
num+=2.8 // output: 10.8
num+=2.8 // output: 13.600000000000001
num+=2.8 // output: 16.400000000000002
num+=6.2 // 22.6
```

The issue seems to be around floating point math rounding that is adding the
additional zeros.

I had thought this was an issue specifically with JavaScript but it
turns out that it is the IEEE 754 floating point specification. I had
confirmed this with a short go program as well.

```
func main(){
  float32 num1=0
  num1+=8
  num1+=2.8
  num1+=2.8
  fmt.Println("%v2f", num1)
  //Output 13.600000000000001
}
```

The crux if the issue is binary floating point arithmetic precision
since computers do not know where to end such as for 1/3.

For JavaScript, there is a ECMA number format API for currencies. Be
aware of browser compatibility. This will not work on IE or safari.

```
var formatterJPY = new Intl.NumberFormat('ja-JP', {
  maximumSignificantDigits: 2,
  style: 'currency',
  currency: 'JPY'
});

console.log(formatterJPY.format(0.2233 + 0.1)); // logs "￥0.32"
```

For Go, I found that using math.Round works okay to round to nearest
decimal place.

There are also a lot of JavaScript libraries that will deal with
floating point arithmetic as well.

Overall, it is wrong to say that JavaScript **cannot** perform floating
point maths when the calculation it is doing is in line with the
IEE 754 specification. Other languages use this as well. I point this
out because I have read / seen multiple incorrect videos that state this
as a fact unfortunately...

Related:

    * [ECMAScript Internationalization API](https://norbertlindenberg.com/
    2012/12/ecmascript-
    internationalization-api/index.html)
    * [JavaScript calculation article](https://www.honeybadger.io/blog/
    currency-money-calculations-in-javascript/)
    * [Mozilla number format docs](https://www.honeybadger.io/blog/
    currency-money-calculations-in-javascript/)
    * [Golang math.Round](https://gosamples.dev/round-float/)

Tags:

  #JavaScript #Math #Golang
