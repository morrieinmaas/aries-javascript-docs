# iOS

> It is presumed that you have a working [React
> Native](https://reactnative.dev) as explained
> [here](https://reactnative.dev/docs/environment-setup).

### Adding the Indy.Framework to a React Native application

> Your iOS target version has to be above 10.0 in order to work

In order for the Aries JavaScript Ecosystem to use the
[indy-sdk](https://github.com/hyperledger/indy-sdk) on iOS the `Indy.Framework`
has to be added.

Due to some issues with manually building this library we have decided to host
a most up-to-date pre-built version. this is located
[here](https://github.com/animo/Indy.Framework).

Adding this to your application is just three simple steps.

First, the [Indy.Framework](https://github.com/animo/Indy.Framework) has to be
cloned.

```console
git clone https://github.com/animo/Indy.Framework
cd Indy.Framework
```

Secondly, we have to add the framework to your React Native project.

```console
mv Indy.framework <YOUR_PROJECT_DIRECTORY>/ios/Pods/Frameworks/Indy.Framework
```

Lastly, a command has to be ran, from the root of your project, to include the
framework.

```console
pod install --project-directory ios
```

Additionally, you need to ensure the following:

- `ENABLE_BITCODE` is set to false
- `Indy.Framework` is added to the project as embedded content

You can set both in XCode.app by navigating to your project settings. `ENABLE_BITCODE` should be disabled by default.
Under the `General` tab in settings you can find `Frameworks, Libraries, and Embedded Content`. Click `+` to open the file selector and add `Indy.Framework` from your Pods.

NOTE: For these steps to work with a react native projects do _not_ follow the instructions in the [indy-sdk repo](https://github.com/hyperledger/indy-sdk) unless you know what you are doing or have some customised setup.