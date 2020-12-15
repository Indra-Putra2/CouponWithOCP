## Coupon with OCP
merupakan aplikasi prehitungan coupon dengan menerapkan ```Open
Close Principle```

## How does it works
```csharp
static void Main(string[] args)
        {
            Coupon coupon1 = new CouponWithNominal(2000);
            Console.WriteLine(coupon1.calculate(10000));

            Coupon coupon2 = new CouponWithPercentage(25);
            Console.WriteLine(coupon2.calculate(10000));

            Coupon coupon3 = new CouponWithMaxNominal(90, 3000);
            Console.WriteLine(coupon3.calculate(10000));

            Coupon coupon4 = new CouponWithCashback(500);
            Console.WriteLine(coupon4.calculate(10000));

        }
```
digunakan untuk menjalankan aplikasi perhitungan coupon

digunakan untuk memasukkan nilai discNominal yg di inputkan

```csharp
public override double calculate(double originPrice)
        {
            return originPrice - discNominal;
        }
```
digunakan untuk menghitung nilai total Coupon dengan nomimal

```csharp
public override double calculate(double originPrice)
        {
            return (100 - discPercentage) * originPrice / 100;
        }
```
digunakan untuk menghitung nilai total Coupon dengan discpercantage

```csharp
public override double calculate(double originPrice)
        {
            double discPercentageInRupiah = discPercentage * originPrice / 100;
            double finalPrice = 0;
            if (discPercentageInRupiah > discNominal)
            {
                finalPrice = originPrice - discNominal;
            }
            else
            {
                finalPrice = originPrice - discPercentageInRupiah;
            }
            return finalPrice;
        }
```
digunakan untuk mengitung total coupon dengan nilai maximum nominal

```csharp
public override double calculate(double originPrice)
        {
            return originPrice - discNominal;
        }
```
digunakan untuk mengitung total coupon dengan cashback
