# Currency iOS : 

### Description:  


```swift


class ViewController: UIViewController {
  
  ...

  @IBAction func calculatePrimeNumbers(_ sender: Any) {
    let queue = OperationQueue()
    queue.addOperation {
      for number in 0 ... 100_000_000 {
        let isPrimeNumber = self.isPrime(number: number)
        print("\(number) is prime: \(isPrimeNumber)")
      }

    }
  }
  
  
  ...  
}


// or 

class CalculatePrimeOperation: Operation {
  
  override func main() {
    for number in 0 ... 100_000_000 {
      let isPrimeNumber = isPrime(number: number)
      print("\(number) is prime: \(isPrimeNumber)")
    }
  }
  
  func isPrime(number: Int) -> Bool {
    if number <= 1 {
      return false
    }
    if number <= 3 {
      return true
    }
    var i = 2
    while i * i <= number {
      if number % i == 0 {
        return false
      }
      i = i + 2
    }
    return true
  }
  
}



```


![imagen](../master/Sketch/CurrencyiOS.gif)  
