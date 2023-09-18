# Debugging SwiftUI Views

Since no one here is a true iOS Developer, our current app is kind of a mess
architecturally (it works though). I've run into a problem where one of the
views I show conditionally is rendered but it's frame properties seem to
"drift". The actual cause/solution is out of the scope of this piece but I
wanted to write about two methods for troubleshooting state changes in SwiftUI
views:

## 1. `Self._printChanges()`

At the top of your view simply put:
```swift
struct ContentView: View {
    @StateObject private var someObject = SomeObservableObject()

    var body: some View {
        let _ = Self._printChanges()
        Text("What could possibly go wrong?")
    }
}
```
Any time a state change triggers a redraw of that view, you'll see a line that
looks something like `ContentView: _someObject changed` in the terminal.


## 2. Random border/background color.
Another trick, is to create an extension to `Color` that adds a computed
property called `random`. It will generate a random color that you can then
assign to an element's `.background` or `.border`.


```swift
extension ShapeStyle where Self == Color {
    static var random: Color {
        Color(
            red: .random(in: 0...1),
            green: .random(in: 0...1),
            blue: .random(in: 0...1)
        )
    }
}
...
struct ContentView: View {
    var body: some View {
        Text("Hello, world!")
            .background(.random)
    }
}
```

Now any time the view's state changes and redraws, the background of the view
will change colors.


SOURCE: [Hacking with Swift](https://www.hackingwithswift.com/quick-start/swiftui/how-to-find-which-data-change-is-causing-a-swiftui-view-to-update)
