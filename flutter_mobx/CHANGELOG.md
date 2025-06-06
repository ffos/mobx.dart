## 2.2.0+1
 - renamed `Observer.withChild` to `Observer.withBuiltChild`
`
## 2.2.0
 - `Observer` is updated with the new `Observer.withBuiltChild` constructor, so you can exclude child branch from the re-rendering. - [@subzero911](https://github.com/subzero911) \
   In case if you use `Observer.withBuiltChild`, you should provide two parameters: `builderWithChild` and `child`:
   ```dart
   Observer.withBuiltChild(
     builderWithChild: (context, child) => FooWidget(foo: foo, bar: child),
     child: BarWidget(), // won't rebuild
   ),
   ``` 

## 2.1.1

- refactor: export `MultiReactionBuilder` from `flutter_mobx.dart` by [@amondnet](https://github.com/amondnet)

## 2.1.0+1

- Patching to update the version in the library file

## 2.1.0

- feat: add `MultiReactionBuilder` widget by [@amondnet](https://github.com/amondnet)

## 2.0.6+3 - 2.0.6+5

- Moved the version into its own file (`version.dart`) and exported from the main library file
- Bringing the `version.dart` file in sync with `pubspec.yaml`
- Updated Changelog to change insecure link

# 2.0.6+2

- Fixed issue in showing issue tracker link on pub.dev

## 2.0.6 - 2.0.6+1

- Adding support for previous versions of Flutter SDK

## 2.0.5+1

- Package upgrades

## 2.0.5

- Improve `debugFindConstructingStackFrame` to let the message be less confusing to the reader
- Allow disabling `No observables detected in the build method of Observer`
- The `analyzer: ^3.0.0` in master branch is incompatible with Flutter stable
- If `builder` of `Observer` errors, further error `LateInitializationError: Local 'built' has not been initialized.` will happen in addition to the actual error, reducing developer experience

## 2.0.4

- Introducing a ReactionBuilder widget that helps you create an inline reaction and eliminates the need
  to have a wrapper-`StatefulWidget` that uses the `initState` to do the same. You can read more in the [docs for ReactionBuilder](https://mobx.netlify.app/api/observers#reactionbuilder-widget).

## 2.0.3 - 2.0.3+2

- Package upgrades
- Minor cleanups
- Adopting the recommended linting for Dart

## 2.0.2

- Moved `analyzer` package to `2.0.0` - @davidmartos96

## 2.0.1

- Moving from `mockito` to `mocktail`

## 2.0.0

- Full support for Null Safety

## 2.0.0-nullsafety.0 - 2.0.0-nullsafety.3

- Null safety support

## 1.1.0+2

- Reformatting for improving the pub.dev score

## 1.1.0 - 1.1.0+1

- Exceptions are reported more reliably with `FlutterError.reportError`. This also includes the stack trace, as all caught exceptions are now wrapped inside `MobXCaughtException`.
- Syncing versions with pubspec.yaml

## 1.0.0 - 1.0.1

- Ready for prime time!
- Fixing version resolution

## 0.3.7

- Refactoring `observer.dart` to separate out the `StatelessObserverWidget`, `StatefulObserverWidget` and the `ObserverWidgetMixin` into their own files.

## 0.3.6+1 - 0.3.6+2

- README updates
- Switching to [Github Actions](https://github.com/mobxjs/mobx.dart/actions) for all builds and publishing
- Upgraded to `Dart 2.7` as the min SDK

## 0.3.5 - 0.3.6

- Updated `mobx` dependency version to **0.4.0** in `flutter_mobx` `pubspec.yaml`
- Improved naming of `Observer` in debug-mode with the correct line in StackTrace.

Thanks to [Scott Hyndman](https://github.com/shyndman) for all the contributions in this release.

## 0.3.4 - 0.3.4+4

- Added two new `Observer`-widgets: `StatelessObserverWidget` and `StatefulObserverWidget`
- Improved the reporting of Flutter errors inside `Observer` widgets.
- Exposing the `debugAddStackTraceInObserverName` field
- Removing the deprecated `authors` field from `pubspec.yaml`

Thanks to [Scott Hyndman](https://github.com/shyndman) and [Remi Rousselet](https://github.com/rrousselGit) for the work done in this release!

## 0.3.3+3

- More documentation comments

## 0.3.2 - 0.3.3+1

- Errors that occur internal to the `setState()` call are now reported via `FlutterError.reportError` so they don't go unnoticed by the user.
- Added a version constant that matches the `pubspec.yaml`

## 0.3.0 - 0.3.1+1

- Adapting to the API changes in `mobx 0.3.0`
- Formatting changes
- Using `StackTrace.current` as the name for an `Observer`, when not provided. This helps in quickly jumping to the location of the `Observer`-usage during debugging.
- Docs update

## 0.2.3+1

- `Observer` is relaying the exception caught during the tracking phase. This is done using the `errorValue` field present on the `reaction` instance.

## 0.2.2

- CHANGELOG updates which got missed out in previous versions
- The `Observer` does not trap exceptions occurring during the `build()` anymore. Previously, this used to be the case, which made it difficult to get proper stack traces.

## 0.2.1+1

- README updates

## 0.2.1

- Upgrading to use the `0.2.1` version of `mobx`, which makes it compatible with the latest `beta`/`dev`/`master` channels

## 0.2.0

- Upgrading to use the `0.2.0` version of `mobx`

### 0.0.2 - 0.1.3

- Warn when no observables are found in the `Observer`'s `builder` function. This was originally an `AssertionError`, which was deemed to be too strong and caused apps to crash in debug mode.
- Updates to tests
- Updates to documentation

## 0.0.1 - First release.

- Observer component that re-renders when reactive variables change.
