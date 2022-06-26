1. install Chocolatey
2. выполняем команды от имени администратора:
   ```
   choco install -y nodejs-lts openjdk11
   ```
3. устанавливаем android studio добавляем эмулятор:
   * https://android-tools.ru/coding/emulyatory-v-android/#:~:text=%D0%94%D0%BB%D1%8F%20%D1%8D%D1%82%D0%BE%D0%B3%D0%BE%20%D0%BD%D1%83%D0%B6%D0%BD%D0%BE%20%D0%B2%20Android,%D0%B2%D1%8B%D0%B1%D1%80%D0%B0%D1%82%D1%8C%20%D1%82%D0%B8%D0%BF%20%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%20%D0%B8%20%D0%BF%D1%80%D0%BE%D1%84%D0%B8%D0%BB%D1%8C.
4. добавляем переменные окружения:
* создаем переменную для пользователя:   
```
setx ANDROID_HOME "C:\Users\user\AppData\Local\Android\Sdk\"
```
* добавляем в path нашу переменную для пользователя:
  ```
  setx path "%path%;%ANDROID_HOME%"
  ```
  ```
  setx path "%path%;%ANDROID_HOME%\platform-tools"
  ```
* глобально с опцией /M
  ```
  setx /M ANDROID_HOME "C:\Users\user\AppData\Local\Android\Sdk\"
  ```
  ```
  setx /M path "%path%;%ANDROID_HOME%"
  ```
  ```
  setx /M path "%path%;%JAVA_HOME%\bin"
  ```

5. создадим проект AwesomeProject:
```
npx react-native init AwesomeProject
```

  предлагает обновить npm:
  ```
  npm install -g npm@8.13.1
  ```

6. запускаем проект:
   ```
   cd "C:\Users\user\Desktop\instructions_for_git\react-native\AwesomeProject" && npx react-native run-android
   ```
   * источники:
   * https://habr.com/ru/company/neoflex/blog/428912/
   *  https://reactnative.dev/docs/environment-setup
   * https://www3.ntu.edu.sg/home/ehchua/programming/howto/Environment_Variables.html
   * https://ip-calculator.ru/blog/ask/change-system-variables-windows-10/
   * https://winaero.com/create-environment-variable-windows-10/
   * http://www.dowdandassociates.com/blog/content/howto-set-an-environment-variable-in-windows-command-line-and-registry/