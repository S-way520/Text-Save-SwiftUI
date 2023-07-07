# Text-Save-SwiftUI
SwiftUI saves and loads text.
# The first part
![IMG_0259](https://github.com/S-way520/Text-Save-SwiftUI/assets/95877651/d5f4f832-fe08-413d-9263-62109eca57ad)
# The second part
Code file 1
```swift
import SwiftUI
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```
Code file 2
```swift
import SwiftUI
struct ContentView: View {
    @State private var text: String = UserDefaults.standard.string(forKey: "SavedText") ?? ""
    var body: some View {
        VStack {
            TextEditor(text: $text)
                .border(Color.gray)
            HStack {
                Button("Save") {saveText()}
                Spacer()
                Button("Load") {loadText()}
            }
            .padding(.horizontal, 50)
        }.padding()
    }
    func saveText() {
        UserDefaults.standard.set(text, forKey: "SavedText")
    }
    func loadText() {
        if let savedText = UserDefaults.standard.string(forKey: "SavedText") {
            text = savedText
        }
    }
}
```
