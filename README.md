# rnw-071-experimental-nuget

Testing experimental nuget in an RNW csharp app with a dependency on an RNW csharp library.

## MyApp (CSharp app)

```
npx react-native init MyApp --template react-native-template-typescript
cd myApp
npx react-native-windows-init --version 0.71 --overwrite --language "cs" --projectType "app" --experimentalNuGetDependency true
```

## MyCSharpNativeModule (CSharp Library)

```
npx react-native init MyCSharpNativeModule --template react-native-template-typescript
cd MyCSharpNativeModule
npx react-native-windows-init --version 0.71 --overwrite --language "cs" --projectType "lib" --experimentalNuGetDependency true
```

## MyCppNativeModule (Cpp Library)

```
npx react-native init MyCppNativeModule --template react-native-template-typescript
cd MyCppNativeModule
npx react-native-windows-init --version 0.71 --overwrite --language "cpp" --projectType "lib" --experimentalNuGetDependency true
```

After creating the packages, MyCSharpNativeModule was added as a MyApp dependency:

```
cd MyApp
yarn add file:../MyCSharpNativeModule
```

Finishing did autolink:

```
npx react-native autolink-windows
```

Using:

- Yarn v1.21.1
- Node v16.13.1
- Windows Powershel v5.1.19041.3031
