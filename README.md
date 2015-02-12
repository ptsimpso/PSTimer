# PSTimer
A simple countdown timer component for iOS apps written in Swift. Just clone or download the repo and drag the PSTimer.swift file into your project.

## Initialization
The `CountdownTimer` class initializer takes a `UILabel`, as well as the minutes and seconds that the timer should start the countdown from. Make sure to adhere to the `CountdownTimerDelegate` protocol and implement the `countdownEnded()` function in order to get notified when the countdown finishes. Example:

```swift
class CustomViewController: UIViewController, CountdownTimerDelegate {

  @IBOutlet weak var timeLabel: UILabel!
  var timer: CountdownTimer!

  override func viewDidLoad() {
    // Timer will start at 15:00
    timer = CountdownTimer(timerLabel: timeLabel, startingMin: 15, startingSec: 0)
    timer.delegate = self
  }

  func countdownEnded() -> Void {
    // Handle countdown finishing
  }
}
```

## Start / Stop
You can start and stop the timer with:

```swift
timer.start() // Begins countdown
timer.pause() // Pauses countdown
timer.reset() // Pauses countdown and resets to the initial time
```

## License
MIT all the way.
