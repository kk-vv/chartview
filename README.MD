### `ZXChartView`

- `IMG`

![img](https://github.com/iFallen/chartview/raw/master/Screenshot/1.gif)

- `Tips`

`init`

```
lineChartView = ZXLineChartView.init(CGPoint(x:0,y:100))
lineChartView.selectedPoint(at: 2)
lineChartView.delegate = self
lineChartView.dataSource = self
self.view.addSubview(lineChartView)
```

`Delegate`

```
extension ViewController:ZXLineChartViewDelegate {
    func zxLineChartView(_ lineChartView: ZXLineChartView, selectedAt index: Int) {
        print("selected:\(index)")
    }
    
    func zxLineChartView(_ lineChartView: ZXLineChartView, animation finished: Bool) {
        print("line animiation finished")
    }
}
```

`DataSource`

```
extension ViewController:ZXLineChartViewDataSource {
    func numberOfValues(in lineChartView: ZXLineChartView) -> Int {
        return values.count
    }
    
    func zxLineChartView(_ lineChartView: ZXLineChartView, valueAt index: Int) -> NSNumber {
        return values[index]
    }
    
    func zxLineChartView(_ lineChartView: ZXLineChartView, titleAt index: Int) -> String {
        return "\(index)"
    }
    /*
    func preValue(in lineChartView: ZXLineChartView) -> NSNumber? {
        //return NSNumber.init(value: 45)
        return nil
    }
    func lastValue(in lineChartView: ZXLineChartView) -> NSNumber? {
        //return NSNumber.init(value: 30)
        return nil
    }
    */
}
```