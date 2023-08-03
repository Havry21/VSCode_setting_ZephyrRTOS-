# Настроки VSCode  для ZephyrRTOS
Перед началом работы в vscode вместе с ZephyrRTOS необходимо установить несколько расширений. Вкладка с расширениями находится в левой боковой панели.

<div align="center">
    <img src="img/vscode_extc.png?raw=true">
</div>

Расширения ищутся при помощи поисковой строки. Список необходимых и допольнительных расширений представлен ниже
### Основные 
- Cortex-Debug
- Cmake
- C/C++
- C/C++ Extension Pack
### Дополнительные(*для удобства*)
- nRF Kconfig - для *Kconfig* и *prj.conf* файлами  
- nRF DeviceTree - для *.dts* и т.д.

# Настройка проекта для vsCode

Для настройки проекта, вам нужно открыть папку с вашим проектом через vsCode или скачать репозиторий, удобнее всего это делать через стартовое окно, открыть его можно при помощи "*Ctrl + Shift + N*".

<div align="center">
    <img src="img/startWindowVsCode.png?raw=true">
</div>

Когда вы открыли проект, добавьте в него папку *.vscode* из этого репозитория, в ней находятся все необходимые настройки для прошивки и отладки микроконтроллеров. 
## Папка .vscode 
Основные файлы
- *launch.json* - основные настройки для прошивки (при удаленной прошивки раскомментить строку ipAddress). **Необходимо** в строке *gdbPath* поменять полный путь к зефировскому gbd. Так же, есть строка device в котором указан МК, ее можно не менять. 
- *.cortex-debug.registers.state.json, c_cpp_properties.json,settings.json* - ничего менять не нужно 
- *task.json* - таски для удобвста сборки проека. 

Под МК в VS code прошивка собирается через терминал, чтобы упростить этот процесс сделаны таски. По факту это просто готовые наборы команд для терминала. Вызвать таску можно несколькими способами

Открыть ее через меню *Terminal -> Run Task* 
<div align="center">
    <img src="img/task_throw_menu.png?raw=true ">
</div>


Через горячии клавиши *Ctrl + Shift + P* набираем *Tasks:Run Task*
<div align="center">
    <img src="img/task_hot_key.png?raw=true ">
</div>

Меню с тасками 

<div align="center">
    <img src="img/task_menu.png?raw=true ">
</div>

## Файл .clang-format 
Настрока стиля 

# Сборка проекта 
1) Добавляем папку **build** в проект 
2) Запускаем таску **cmake**, если в CMakeLists не указана плата под которую собирается нужно поправить таску *cmake* добавив в строку *"command"* cmake -DBOARD=<ваша плата> ..
3) Запускаем таску **make**. Таска **make** имеет значение параметра default - true, поэтому ее можно вызывать через клавиши "*Ctrl + Shift + B*"

Если все сделано правильно, то вы увидете внизу VScode что-то похожее

<div align="center">
    <img src="img/build_result.png?raw=true ">
</div>

Чтобы запустить отладку откройте вкладку *Run and Debug* и нажмите на кнопку *Start Debugging*
<div align="center">
    <img src="img/debug_menu.png?raw=true ">
</div>

Так же запустить отладку можно через **F5**