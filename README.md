# vcpkg-qt5-qml-bug

## How to reproduce

1. Clone vcpkg to `C:/src/vcpkg`
2. Install dependencies

    ```powershell
    .\vcpkg.exe install qt5:x64-windows
    ```

3. Configure and Build

    ```powershell
    & "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe" --no-warn-unused-cli -DCMAKE_EXPORT_COMPILE_COMMANDS:BOOL=TRUE -Hc:/Users/ming/projects/vcpkg-qt5-qml-bug -Bc:/Users/ming/projects/vcpkg-qt5-qml-bug/build -G "Visual Studio 16 2019" -T host=x64 -A x64

    & "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe" --build c:/Users/ming/projects/vcpkg-qt5-qml-bug/build --config Debug --target ALL_BUILD -- /maxcpucount:14
    ```

4. See the error

    ```powershell
    > .\build\Debug\vcpkg-qt5-qml-bug.exe
    QML debugging is enabled. Only use this in a safe environment.
    QQmlApplicationEngine failed to load component
    qrc:/main.qml:1:1: plugin cannot be loaded for module "QtQuick": Cannot load library C:\Users\ming\projects\vcpkg-qt5-qml-bug\build\Debug\qml\QtQuick.2\qtquick2plugind.dll: The specified module could not be found.
    ```
