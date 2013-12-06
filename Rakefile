# -*- coding: utf-8 -*-
$:.unshift("/Library/RubyMotion/lib")
require 'motion/project/template/ios'
require "rubygems"
require 'bundler'
Bundler.require

Motion::Project::App.setup do |app|
  # Use `rake config' to see complete project settings.
  app.name = 'Texties'
  app.deployment_target = "7.0"
  app.device_family = [:iphone]
  app.interface_orientations = [:portrait, :portrait_upside_down]
  app.identifier = 'com.mohawkapps.texties'
  app.version = "1"
  app.short_version = "0.0.1"
  app.icons = Dir.glob("resources/Icon*.png").map{|icon| icon.split("/").last}
  app.prerendered_icon = true
  app.info_plist['APP_STORE_ID'] = 769404785

  app.pods do
    pod 'UIActionSheet+Blocks'
  end

  app.development do
    app.entitlements['get-task-allow'] = true
    app.codesign_certificate = "iPhone Developer: Mark Rickert (YA2VZGDX4S)"
    app.provisioning_profile = "./provisioning/TextiesDevelopment.mobileprovision"

    app.testflight do
      app.testflight.sdk = 'vendor/TestFlightSDK'
      app.testflight.api_token = 'b2a3667268f446b35c4ab473259912c9_MTUwNjI'
      app.testflight.team_token = '2cf18a21ce6f6ccef94c49811c719285_MzA5NjUwMjAxMy0xMi0wNSAxODowMDoxMy4yODE0NzE'
      # app.testflight.notify = true # default is false
      # app.testflight.identify_testers = true # default is false
    end

    # app.pods do
    #   pod "Reveal-iOS-SDK"
    # end
  end

  app.release do
    app.entitlements['get-task-allow'] = false
    app.codesign_certificate = "iPhone Distribution: Mohawk Apps, LLC (DW9QQZR4ZL)"
    app.provisioning_profile = "./provisioning/TextiesDistribution.mobileprovision"
  end
end
