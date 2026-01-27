# iOS (Xcode/Swift)

## Detection signals
- `Package.swift`
- `*.xcodeproj` or `*.xcworkspace`
- `Podfile`, `Cartfile`
- `Project.swift`, `Tuist/`
- `fastlane/Fastfile`
- `*.xcconfig`
- `Sources/` or `Tests/` (SPM layouts)

## Multi-module signals
- Multiple targets/projects in `*.xcworkspace` or `*.xcodeproj`
- `Package.swift` with multiple targets/products
- `Sources/<TargetName>` and `Tests/<TargetName>` layout
- `Project.swift` defining multiple targets (Tuist)

## Before generating, analyze these sources
- `Package.swift` (SPM)
- `*.xcodeproj/project.pbxproj` or `*.xcworkspace/contents.xcworkspacedata`
- `Podfile`, `Cartfile` (if present)
- `Project.swift` / `Tuist/` (if present)
- `fastlane/Fastfile` (if present)
- `Sources/` and `Tests/` layout for targets

## Codebase scan (iOS-specific)
- Source roots: `Sources/`, `Tests/`, `ios/` (if present)
- Feature/layer folders (record only if present):
  `Features/`, `Core/`, `Services/`, `Networking/`, `UI/`, `Domain/`, `Data/`
- SwiftUI usage (record only if present):
  `@main`, `App`, `@State`, `@StateObject`, `@ObservedObject`,
  `@Environment`, `@EnvironmentObject`, `@Binding`
- UIKit/lifecycle (record only if present):
  `UIApplicationDelegate`, `SceneDelegate`, `UIViewController`
- Combine/concurrency (record only if present):
  `@Published`, `Publisher`, `AnyCancellable`, `@MainActor`, `Task`

## Mandatory output (iOS module CLAUDE.md)
Include these if detected (list actual names found):
- **Features inventory**: list dirs under `Features/` or feature targets
- **Core modules**: list dirs under `Core/`, `Services/`, `Networking/`
- **Navigation**: list coordinators, routers, or SwiftUI navigation files
- **DI container**: list DI setup (Swinject, Factory, manual containers)
- **Network layer**: list API clients or networking services
- **Persistence**: list CoreData models or other storage classes

## Command sources
- README/docs or CI invoking Xcode or Swift tooling
- Repo scripts that call Xcode/Swift tools
- `xcodebuild`, `swift build`, `swift test` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `Sources/`, `Tests/`
- `fastlane/`
- `ios/` (React Native or multi-platform repos)
