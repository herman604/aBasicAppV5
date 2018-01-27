platform :ios, '9.0'

project 'aBasicAppV5.xcodeproj'
target 'aBasicAppV5' do

source 'https://github.com/CocoaPods/Specs.git'

use_frameworks!

# NB: get rid of next line once FMDB works with xcode 9
pod 'FMDB', :git => 'https://github.com/forcedotcom/fmdb', :branch => '2.7.2_xcode9' 

pod 'SalesforceAnalytics', :path => 'mobile_sdk/SalesforceMobileSDK-iOS'
pod 'SalesforceSDKCore', :path => 'mobile_sdk/SalesforceMobileSDK-iOS'
pod 'SmartStore', :path => 'mobile_sdk/SalesforceMobileSDK-iOS'
pod 'SmartSync', :path => 'mobile_sdk/SalesforceMobileSDK-iOS'

end

# Fix for xcode9/fmdb/sqlcipher/cocoapod issue - see https://discuss.zetetic.net/t/ios-11-xcode-issue-implicit-declaration-of-function-sqlite3-key-is-invalid-in-c99/2198/27
post_install do | installer |
  print "SQLCipher: link Pods/Headers/sqlite3.h"
  system "mkdir -p Pods/Headers/Private && ln -s ../../SQLCipher/sqlite3.h Pods/Headers/Private"
end
