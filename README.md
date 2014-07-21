swiftspec
=========

swiftspec

Implementation

```swift
class Car
  let name: String
  let Engine: Engine
  
  init(name: String) {
    self.name   = name
    self.engine = Engine()
  }
  
  func tootHorn() -> String {
    return "TOOT!"
  }
  
  func start() {
    engine.run()
  }
  
  class Engine
    var isRunning: Bool
    
    func run() {
      self.isRunning = true
    }
  }
}
```

Spec

```swift
Spec.describe(Car) {
  let subject = Car(name: "K.I.T.T")
  
  its("name") { isExpected.toEqual("K.I.T.T") }
  
  specify("tootHorn") { isExpected.toReturn("TOOT!") }
  
  describe("start") {
    it("runs its engine") {
      expect(subject.engine).toReceive("run")
      
      subject.start()
    }
  }
}
```

