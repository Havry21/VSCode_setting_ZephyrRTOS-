# Настроки VSCode  для ZephyrRTOS
##  Расширения для  VSCode 
### Основные 
- Cortex-Debug
- Cmake
- C/C++
- C/C++ Extension Pack
### Дополнительные(*для удобства*)
- nRF Kconfig - для *Kconfig* и *prj.conf* файлами  
- nRF DeviceTree - для *.dts* и т.д.

## Папка .vscode 
Основные файлы
- *launch.json* - основные настроки для прошивки (при удаленной прошивки раскомментить строку ipAddress)
- *.cortex-debug.registers.state.json, c_cpp_properties.json,settings.json* - ничего менять не нужно 
- *task.json* - таски для удобвста сборки и прошивки кода. Таска **make** имеет значение параметра defaul - true, ее можно вызывать через клавиши "*Ctrl + Shift + B*"

## Файл .clang-format 
Настрока стиля 

# Сборка проекта через Tasks
1) Добавляем папку **build**
2) Запускаем таску **cmake** (*Terminal -> Run Task* или *Ctrl + Shift + P* набираем *Tasks:Run Task*)
3) Запускаем таску **make** 