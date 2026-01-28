# iOS (Xcode/Swift)

## Detection signals
- `*.xcodeproj`, `*.xcworkspace`
- `Package.swift` (SPM)
- `Podfile`, `Podfile.lock` (CocoaPods)
- `Cartfile` (Carthage)
- `*.pbxproj`
- `Info.plist`

## Multi-module signals
- Multiple targets in `*.xcodeproj`
- Multiple `Package.swift` files
- Workspace with multiple projects
- `Modules/`, `Packages/`, `Features/` directories

## Pre-generation sources
- `*.xcodeproj/project.pbxproj` (target list)
- `Package.swift` (dependencies, targets)
- `Podfile` (dependencies)
- `*.xcconfig` (build configs)
- `Info.plist` files

## Codebase scan patterns

### Source roots
- `*/Sources/`, `*/Source/`
- `*/App/`, `*/Core/`, `*/Features/`

### Layer/folder patterns (record if present)
`Models/`, `Views/`, `ViewModels/`, `Services/`, `Networking/`, `Utilities/`, `Extensions/`, `Coordinators/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| SwiftUI View | `struct *: View`, `var body: some View` | swiftui-view |
| UIKit VC | `UIViewController`, `viewDidLoad()` | uikit-viewcontroller |
| ViewModel | `@Observable`, `ObservableObject`, `@Published` | viewmodel-observable |
| Coordinator | `Coordinator`, `*Coordinator` | coordinator-pattern |
| Repository | `*Repository`, `protocol *Repository` | data-repository |
| Service | `*Service`, `protocol *Service` | service-layer |
| Core Data | `NSManagedObject`, `@NSManaged`, `.xcdatamodeld` | coredata-entity |
| Realm | `Object`, `@Persisted` | realm-model |
| Network | `URLSession`, `Alamofire`, `Moya` | network-client |
| Dependency | `@Inject`, `Container`, `Swinject` | di-container |
| Navigation | `NavigationStack`, `NavigationPath` | navigation-swiftui |
| Combine | `Publisher`, `AnyPublisher`, `sink` | combine-publisher |
| Async/Await | `async`, `await`, `Task {` | async-await |
| Unit Test | `XCTestCase`, `func test*()` | xctest |
| UI Test | `XCUIApplication`, `XCUIElement` | xcuitest |

## Mandatory output sections

Include if detected:
- **Targets inventory**: list from pbxproj
- **Modules/Packages**: SPM packages, Pods
- **View architecture**: SwiftUI vs UIKit
- **State management**: Combine, Observable, etc.
- **Networking layer**: URLSession, Alamofire, etc.
- **Persistence**: Core Data, Realm, UserDefaults
- **DI setup**: Swinject, manual injection

## Command sources
- README/docs with xcodebuild commands
- `fastlane/Fastfile` lanes
- CI workflows (`.github/workflows/`, `.gitlab-ci.yml`)
- Common: `xcodebuild test`, `fastlane test`
- Only include commands present in repo

## Key paths
- `*/Sources/`, `*/Tests/`
- `*.xcodeproj/`, `*.xcworkspace/`
- `Pods/` (if CocoaPods)
- `Packages/` (if SPM local packages)
