add_swift_library(swiftWatchKit ${SWIFT_SDK_OVERLAY_LIBRARY_BUILD_TYPES} IS_SDK_OVERLAY
  WatchKit.swift

  SWIFT_COMPILE_FLAGS "${SWIFT_RUNTIME_SWIFT_COMPILE_FLAGS}"
  LINK_FLAGS "${SWIFT_RUNTIME_SWIFT_LINK_FLAGS}"
  TARGET_SDKS IOS IOS_SIMULATOR WATCHOS WATCHOS_SIMULATOR
  SWIFT_MODULE_DEPENDS Foundation UIKit CoreGraphics
  SWIFT_MODULE_DEPENDS_WATCHOS HomeKit SceneKit
  FRAMEWORK_DEPENDS_WEAK WatchKit
  SWIFT_COMPILE_FLAGS_WATCHOS -Xfrontend -disable-autolink-framework -Xfrontend CoreText
)
