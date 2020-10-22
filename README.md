# Readme.md

## Failures

### Basic setup

Podfile:

```
target 'SampleEarlGrey2' do
  use_frameworks!
  
  pod 'EarlGreyApp', git: 'https://github.com/google/EarlGrey', branch: 'earlgrey2'

  target 'SampleEarlGrey2UITests' do
    pod 'EarlGreyTest', git: 'https://github.com/google/EarlGrey', branch: 'earlgrey2'
  end
end
```

Result: 

Host app crashes when running unit tests:

```
dyld: could not load inserted library '@executable_path/Frameworks/AppFramework.framework/AppFramework' because image not found

dyld: launch, loading dependent libraries
DYLD_SHARED_CACHE_DIR=/Users/rob/Library/Developer/CoreSimulator/Caches/dyld/19H2/com.apple.CoreSimulator.SimRuntime.iOS-14-0.18A372
DYLD_ROOT_PATH=/Applications/Xcode-12.app/Contents/Developer/Platforms/iPhoneOS.platform/Library/Developer/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot
DYLD_LIBRARY_PATH=/Users/rob/Library/Developer/Xcode/DerivedData/SampleEarlGrey2-elhzpywxzgfrwqdjsjhhhnuathcf/Build/Products/Debug-iphonesimulator
DYLD_INSERT_LIBRARIES=@executable_path/Frameworks/AppFramework.framework/AppFramework:/Applications/Xcode-12.app/Contents/Developer/Platforms/iPhoneOS.platform/Library/Developer/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/usr/lib/libMainThreadChecker.dylib
DYLD_FALLBACK_FRAMEWORK_PATH=/Applications/Xcode-12.app/Contents/Developer/Platforms/iPhoneOS.platform/Library/Developer/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/System/Library/Frameworks
```
