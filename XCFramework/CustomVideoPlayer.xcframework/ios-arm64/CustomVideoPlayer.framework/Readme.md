
xcodebuild archive \
  -scheme CustomVideoPlayer \
  -configuration Release \
  -destination "generic/platform=iOS" \
  -archivePath "./build/CustomVideoPlayer-iOS.xcarchive" \
  SKIP_INSTALL=NO \
  BUILD_LIBRARY_FOR_DISTRIBUTION=YES


xcodebuild -create-xcframework \
  -framework ./build/CustomVideoPlayer-iOS.xcarchive/Products/Library/Frameworks/CustomVideoPlayer.framework \
  -output ./build/CustomVideoPlayer.xcframework
