Appium for Ruby
To make it possible to run Appium tests simply follow these steps
- **brew install node** # get node.js
- **npm install -g appium** # get appium
- **npm install wd** # get appium client
- **appium &** # start appium
- **xcodebuild -sdk iphonesimulator** # build your project and create the .app file
- **bundle exec ruby mytest.rb** # and run your test using bundler

You have to create the .app files for every simulator/os version and run the test script using the generated .app file. There's no option to run on multiple simulators.
The AppPath (path to the .app file) has to be added to the appium driver's desired capabilities. 

eg.:
The start of the main ruby base appium test file
    APP_PATH = '../../../../AppiumSwiftTestApp/build/release-iphonesimulator/AppiumSwiftTestApp.app'

    desired_caps = {
      caps:       {
        platformName:  'iOS',
        versionNumber: '7.1',
        deviceName:    'iPhone Simulator',
        app:           APP_PATH,
      },
      appium_lib: {
        sauce_username:   nil, # don't run on Sauce
        sauce_access_key: nil
      }
    }

    # Start the driver
    Appium::Driver.new(desired_caps).start_driver

aztan futtatni, az appium driver desired capabilities-ben kell az app path
a test ha elszall a session nem torlodi!!!

run java (junit test):
- **brew** # install brew
- **appium** # install appium and run server
- **maven (https://raw.githubusercontent.com/Homebrew/homebrew-versions/master/maven31.rb)** # install maven
- **mvn test** # run the test

node js:
- **npm install underscore q express colors chai-as-promised chai** 
- **npm install appium mocha -g** 