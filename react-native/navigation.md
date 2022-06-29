* источники:
  * https://reactnavigation.org/docs/getting-started/
* установим библиотеки: ( первый вариант если bare React Native project, второй если expo)
* 
   
  ```
  npm install react-native-screens react-native-safe-area-context
  ```
```
expo install react-native-screens react-native-safe-area-context
```

* периодически между командами получал сообщения об ошибках и просьбу пофиксить их выполнить :
```
  npm audit fix --force 
```
  пример ошибок:

```
PS C:\Users\user\Desktop\instructions_for_git\react-native\AwesomeProject> npm install @react-navigation/native
npm WARN config global `--global`, `--local` are deprecated. Use `--location=global` instead.
npm ERR! code ERESOLVE
npm ERR! ERESOLVE unable to resolve dependency tree
npm ERR!
npm ERR! While resolving: AwesomeProject@0.0.1
npm ERR! Found: react@18.0.0
npm ERR! node_modules/react
npm ERR!   react@"18.0.0" from the root project
npm ERR!   peer react@"*" from @react-navigation/native@6.0.10
npm ERR!   node_modules/@react-navigation/native
npm ERR!     @react-navigation/native@"*" from the root project
npm ERR!
npm ERR! Could not resolve dependency:
npm ERR! peer react@"16.8.6" from react-native@0.60.6
npm ERR! node_modules/react-native
npm ERR!   react-native@"^0.60.6" from the root project
npm ERR!   peer react-native@"*" from @react-navigation/native@6.0.10
npm ERR!   node_modules/@react-navigation/native
npm ERR!     @react-navigation/native@"*" from the root project
npm ERR!
npm ERR! Fix the upstream dependency conflict, or retry
npm ERR! this command with --force, or --legacy-peer-deps
npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
npm ERR!
npm ERR! See C:\Users\user\AppData\Local\npm-cache\eresolve-report.txt for a full report.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\user\AppData\Local\npm-cache\_logs\2022-06-26T18_42_40_160Z-debug-0.log
PS C:\Users\user\Desktop\instructions_for_git\react-native\AwesomeProject> npm audit fix --force
  ```


* также понадобиться еще несколько билиотек для навигации:
*  библиотека Stack Navigator https://reactnavigation.org/docs/stack-navigator/
```
npm install @react-navigation/stack
```
```
expo install react-native-gesture-handler
```

* Native Stack Navigator
```
npm install @react-navigation/native-stack
```

* Drawer Navigator
```
npm install @react-navigation/drawer
```
```
expo install react-native-gesture-handler react-native-reanimated
```
* Bottom Tabs Navigator
```
npm install @react-navigation/bottom-tabs
```