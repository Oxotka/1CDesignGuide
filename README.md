[![OpenYellow](https://img.shields.io/endpoint?url=https://openyellow.neocities.org/badges/4/799152816.json)](https://openyellow.notion.site/openyellow/24727888daa641af95514b46bee4d6f2?p=27e2878921a84be3805410324117c660&amp;pm=s) [![Static Badge](https://img.shields.io/badge/my%20telegram-channel-green)](https://t.me/AriN1C) [![Static Badge](https://img.shields.io/badge/infostart-profile-green)](http://infostart.ru/profile/237528/)

<img src=img/designGuide.png width=900>

# Гайд для создания форм на 1С

**Цель** - улучшить качество интерфейсных решений в среде 1С

**Гайд** - это инструкция по дизайну форм в среде 1С. Он охватывает рекомендации и стандарты для оптимизации пользовательского интерфейса. В гайде содержатся указания по использованию элементов интерфейса, включая как основные, так и продвинутые аспекты. Предоставляются также примеры и антипримеры для наглядного понимания принципов дизайна

- [Гайд для создания форм на 1С](#гайд-для-создания-форм-на-1с)
  - [Элементы формы](#элементы-формы)
    - [Декорация](#декорация)
      - [Декорация-надпись](#декорация-надпись)
      - [Декорация-картинка](#декорация-картинка)
    - [Поле ввода](#поле-ввода)
    - [Флажок](#флажок)
    - [Выключатель (Тогл, Свитчер)](#выключатель-тогл-свитчер)
    - [Переключатель](#переключатель)
    - [Тумблер](#тумблер)
    - [Гиперссылки](#гиперссылки)
    - [Кнопка](#кнопка)
    - [Табличная часть](#табличная-часть)
    - [Диалоговое окно](#диалоговое-окно)
    - [Подсказка и расширенная подсказка](#подсказка-и-расширенная-подсказка)
  - [Компоновка формы](#компоновка-формы)
    - [Группы](#группы)
      - [Обычная группа](#обычная-группа)
      - [Свертываемая группа](#свертываемая-группа)
      - [Всплывающая группа](#всплывающая-группа)
    - [Командная панель](#командная-панель)
    - [Команды формы](#команды-формы)
    - [Шапка формы](#шапка-формы)
    - [Подвал формы](#подвал-формы)
    - [Условное оформление](#условное-оформление)
  - [Дополнительные материалы](#дополнительные-материалы)
  - [Вопросы и пожелания](#вопросы-и-пожелания)
  - [Благодарность](#благодарность)

## Элементы формы

### Декорация

Декорация - это базовый элемент для вывода текста

<img src=img/usualLabel.png width=500>

#### Декорация-надпись

Обычно используется как подсказка на форме с помощью форматированной строки

<img src=img/formatString.png width=500>

1. Не ставьте точку в конце, если текст состоит из одного предложения
2. Не используйте декорацию если она, не выполняет полезное действие
3. Не используйте декорацию для установки заголовки простых полей. В этом случае не срабатывает автофокус на поле и часто забывают поставить двоеточие в заголовке поля
4. Не используйте декорацию для выравнивания элементов. Используйте для этого свойства [Групп](#группы)

[↑ Наверх](#гайд-для-создания-форм-на-1с)

#### Декорация-картинка

Обычно используется для иллюстрации чего-либо, а также для привлечения внимание пользователя

 <img src=img/pictureLabel.png width=500>

1. Используйте картинку в составе форматированной строки или отдельным элементом
2. Не используйте картинку из файла, добавьте ее в библиотеку картинок

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Поле ввода

Поле ввода - это базовый элемент для ввода значений

 <img src=img/inputField.png width=500 border=1>

1. Установите ширину поля такой, чтобы вмешалось самое длинное значение из списка
2. Добавьте кнопку Очистки (x), если в поле ввода предусмотрено удаление или пустое значение, кроме отборов на формах, там используется флажок
3. Опишите подсказку ввода для пустого значения на форме, если предусмотрено пустое значение

    <img src=img/inputClearButton.png width=500 border=1>

4. Добавьте кнопку выбора для строковых полей ввода, если есть из чего выбрать, например, выбор Пути к файлу или Наименования
5. Используйте многострочное поле ввода для строковых значений длинее 100 символов. Установите заголовок для многострочного поля сверху
6. Сохраняйте значения выбранные пользователем для реквизитов формы, если они повторяются, например, поля с периодом или Организацией
7. Не показывайте заголовок у поля Организация или Банковский счет для сокращения места, например, в шапке отчета. Пользователь знает свою организацию и может понять что в этом поле по выбранному значению
8. Добавляйте подсказку ввода, в случае если не показываете заголовок. Для Организаций в отчете напишите "По всем организациям" - покажите поведение пустого поля

    <img src=img/organization.png width=500 border=1>

9. Не используйте платформенный выбор типа для составных типов. Добавьте отдельный выбор типа, например, Контрагент или Физическое лицо
10. Не делайте поле выбора для одного значения - заполните реквизит самостоятельно, а поле скройте функциональной опцией

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Флажок

Флажок используем для включения или выключения опции

<img src=img/checkboxTitle.png width=450 border=1>

1. Установите заголовок флажка справа. Отойдите от умолчания платформы
2. Зона действия флажка, с точки зрения интерфейса, небольшая или отсутствует. Например, при включении флажка можно включить доступность соседнего реквизита или гиперссылки. Если требуется влиять на форму сильнее, используйте [Выключатель](#выключатель-тогл-свитчер) или [Переключатель](#переключатель)
3. Используйте флажок для простой опции, в которой понятно, что означают оба состояния. Если из названия сложно понять действие флажка, то можно добавить подсказку снизу
4. Не используйте флажок для сложных опций, в которых не очевидны оба состояния. Используйте для этого [Переключатель](#переключатель)
5. Не используйте в заголовке флажка отрицательные формулировки, потому что пользователю сложнее понять выключенный флажок, например, «Не Не проводить документ при записи»

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Выключатель (Тогл, Свитчер)

Выключатель переключает состояние формы, реквизита или настройки. Например, включает или выключает опцию. Это вид флажка и к нему применяются правила [Флажка](#флажок)

Выключатель заимствован из мобильных операционных систем, где он используется для включения и выключения настроек

<img src=img/toggle.png width=350 border=1>

1. Используйте выключатель, если при переключении состояния действие происходит сразу и не нужны дополнительные подтверждения
2. Выключатель ассоциируется с большим влиянием, чем флажок. При изменении состояния действие на форму может быть более обширным
3. Не используйте на одной странице больше 2-3 выключателей

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Переключатель

Переключатель используется для выбора одного значения из перечисленных

<img src=img/radiobuttons.png width=500 border=1>

1. Используйте переключатель когда значений немного - от 2 до 5, если больше, используйте [Поле ввода](#поле-ввода) со списком значений
2. Установите значение по умолчанию первым в списке
3. Добавьте подсказки к значениям переключателя для сложных опций

    Для этого создайте два элемента формы с путем к одному реквизиту, у каждого элемента можно сделайте свою подсказку

    <details><summary>Как выглядит в конфигураторе</summary>
    <img src=img/radiobuttonsWithHints.png width=500 border=1>
    </details>

4. Выносите повторяющиеся тексты значений переключателя в заголовок

    <img src=img/radiobuttonPeriods.png width=500 border=1>

5. Переключатель действует на то, что находится справа и под ним

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Тумблер

Тумблер используется для выбора одного значения из перечисленных. Аналогичен [Переключателю](#переключатель)

<img src=img/switcher.png width=600 border=1>

1. Используйте тумблер для 3-5 значений
2. Используйте тумблер, если от выбранных значений перестраивается форма под ним или выполняется какое-то действие, потому что тумблер выглядит как кнопки
3. Тумблер выглядит компактнее, чем [Переключатель](#переключатель) и подходит для коротких значений
4. Не используйте в значениях тумблера повторяющиеся слова, вынесите их в заголовок
5. Не используйте тумблер для 2 значений - не ясно какой пункт выбран

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Гиперссылки

Гиперссылка используется для перехода к другой форме. Пользователю привычно, что по гиперссылке он куда-то перейдет или откроется новая форма и будет потерян фокус с основной формой

<img src=img/hyperlink.png width=300 border=1>

1. Используйте для открытия подчиненных и служебных форм. Например, настройка НДС
2. Давайте осмысленное и достаточно длинное название гиперссылке, чтобы в нее можно было удобно нажать
3. Из гиперссылки должно быть понятно, куда она ведет
4. Не выполняйте действия на форме с помощью гиперссылки. Используйте для этого [Кнопки](#кнопка)
5. Не пишите в гиперссылке слова "здесь", "тут" или "подробнее"
6. Не ставьте две ссылки подряд - трудно заметить переход между двумя ссылками
7. Не меняйте цвет гиперссылки, за исключением ссылок с предупреждением

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Кнопка

Кнопка используется для выполнения действия на форме

<img src=img/button.png width=150 border=1>

1. Используйте кнопку для выполняения действие по запросу пользователя
2. Используйте кнопку с пометкой для команды, связанной со строкой списка (табличная часть или динамический список), например "Использовать как основной"

    <img src=img/buttonUseAsDefault.png width=500 border=1>

3. Сделайте понятный заголовок для кнопки, не пытайтесь сделать его коротким. В случае если по кнопке будет открываться новая форма (не рекомендуется), то название кнопки должно сообщать об этом. Например, "Показать настройки"
4. Используйте кнопку Без фигуры для команд, которые не рекомендуется выполнять или когда кнопок слишком много. Следует использовать с осторожностью
Подробнее про [отображение кнопок без фигур](https://t.me/AriN1C/46)
5. Не используйте кнопку для перехода к другой форме, используйте для этого [Гиперссылку](#гиперссылки)

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Табличная часть

Табличные части используются для хранения и управления множеством связанных записей внутри одного объекта

<img src=img/table.png width=800 border=1>

1. Делайте заголовок табличной части в 1 строку. При необходимости вывести сложный заголовок выводите подсказки в самой таблице, в строке. Например, см. Корректировка реализации

    <img src=img/complicateTitle.png width=200 border=1>

2. Уберите заголовок табличной части, если в ней всего одна колонка. Опишите декорацией содержание табличной части, если это требуется
3. Добавьте в табличной части пустую последнюю колонку, чтобы управлять шириной табличной части. Отключите заголовок у этой колонки, включите "Только просмотр" и установите "Растягивать по горизонтали"

    <img src=img/blankColumn.png width=200 border=1>

4. Прижимайте заголовок колонки табличной части к значению, например, для Числа прижмите вправо, а для Строка или Ссылка - слева (по умолчанию)

5. Ознакомьтесь со стандартом для проектирования интерфейсов - <https://its.1c.ru/db/v8std/content/717/hdoc>

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Диалоговое окно

Диалоговое окно открывается для вопроса или предупреждения пользователю. Это блокирующее сообщение, которое требует обязательного внимания пользователя.
Обычно выводится для необратимых действий, например, очистка табличной части или установка особого режима работы.
Следует использовать с осторожностью!

<img src=img/dialog.png width=600>

1. Уделите особое внимание тексту в диалоговом окне. Опишите подробно в тексте, что требуется от пользователя, добавьте четкий вопрос с однозначным ответом
2. Опишите утвердительное действие, чтобы пользователь однозначно понял о том, что будет выполнено. Для этого установите текст этой кнопки, чтобы он повторял запрашиваемое действие
3. Обрабатывайте закрытие диалогового окна по крестику справа вверху. Для этого установите одну из команд диалогового окна как КодВозвратаДиалога.Отмена

    ```BSL
    &НаКлиенте 
    Асинх Процедура ЗадатьВопрос()
  
    ТекстВопроса = 
        "Для отключения уведомлений и комфортной работы рекомендуем использовать режим тишины.
        |В этом режиме будут приходить только важные уведомления
        |
        |Установить режим тишины?";
  
    Кнопки = Новый СписокЗначений;
    Кнопки.Добавить(КодВозвратаДиалога.Да, "Установить режим тишины");
    Кнопки.Добавить(КодВозвратаДиалога.Отмена, "Нет, оставить как есть");
  
    Результат = Ждать ВопросАсинх(ТекстВопроса, Кнопки);
  
    Если Результат = КодВозвратаДиалога.Да Тогда
        Сообщить("Режим тишины установлен");
    КонецЕсли;
  
    КонецПроцедуры
    ```

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Подсказка и расширенная подсказка

У большинства элементов есть свойство Подсказка, которая выводится в зависимости от свойства Отображение подсказки.
Подсказка - это обычная строка, но можно включить Расширенную подсказку, чтобы использовать форматированную строку. Для этого на элементе формы следует нажать на правую кнопку мыши и выбрать пункт Показать расширенную подсказку

1. Используйте для разовых подсказок отображение через кнопку. Если пользователь видит новый ему элемент и сомневается, что с ним делать, ему достаточно один раз посмотреть подсказку по кнопке, чтобы разобраться. Позже он сможет вернуться к этой подсказке, если потребуется

    <img src=img/buttonHint.png width=700 border=1>

2. Используйте подсказка сверху о всей форме, если она используется не часто. У пользователя такая подсказка будет всегда перед глазами. Например, если это форма с настройками правил

    <img src=img/underHint.png width=700 border=1>

3. Сделайте подсказку снизу для сложных элементов, чтобы объяснить пользователю, что этот реквизит означает. Важно давать подсказки на важные элементы формы, чтобы подчеркнуть их важность
4. Используйте различные средства оформления для акцентирования внимания на конкретный реквизит, например, желтый фон или картинки
5. Подсказок много не бывает, но они не должны быть навязчивыми

[↑ Наверх](#гайд-для-создания-форм-на-1с)

## Компоновка формы

### Группы

Группы используются для объединения элементов вместе. Группы позволяют управлять расположением и выводом элементов

#### Обычная группа

1. Проверьте уместность отображения заголовка у группы, в большинстве случае он не требуется
2. Уберите из заголовка слово "Группа", которое добавляет платформа

    <img src=img/groupTitle.png width=400 border=1>

3. Уберите подсказки в группе созданные платформой по умолчанию - они выводится при удержании курсора над группой
4. Избегайте Расположение - **Горизонтально, если возможно**. Исходите из минимально допустимого расширения 1280х768px
5. Изучите типы выделения обычной группы. Сильное выделение - добавляется полоса и отступ у подчиненных реквизитов, Обычное выделение и Слабое выделение - крупный заголовок

   <img src=img/highlightGroup.png width=500 border=1>

6. Используйте обычное выделение, если нужно сделать больший отступ вокруг группы. [Подробнее о слабом и обычном отображении групп](https://t.me/Aripovn/31)

   <img src=img/representationGroup.gif width=500>

7. Используйте свойство - **Выравнивание элементов и заголовков** для прижатия элементов к одному из краев

[↑ Наверх](#гайд-для-создания-форм-на-1с)

#### Свертываемая группа

Свертываемая группа позволяет скрыть реквизиты внутри сворачиваемого блока

<img src=img/collapsibleGroupTitle.png width=500 border=1>  

1. Используйте свертываемаю группу, чтобы скрыть элементы - это делает форму компактнее и удобнее для работы.
Также смотри стандарт - [Оформление групп разделов с настройками и справочниками](https://its.1c.ru/db/v8std/content/753/hdoc)

2. Давайте описание содержащихся реквизитов в заголовке свертываемой группы, например, Банковский счет и Адрес:

    <img src=img/titleOnGroup.png width=700 border=1>

   В случае если в группе находятся только команды или гиперссылки (см. пример в Администрирование в БСП), то заголовок свернутой группы необязательно заполнять. В этом случае мы упрощаем навигацию по форме для пользователя

3. Снимите флаг "Отображать отступ слева" у свертываемой группы, чтобы элементы были вровень с остальными реквизитами формы

4. Лайфхак для программного управлением свойства группы Свернута. Управлять этим свойством программно нельзя, но можно создать две группы с одинаковыми реквизитами, одна по умолчанию свернута, а другая по умолчанию развернута. ПриСозданииНаСервере следует проверить какую группу показать пользователю

5. Не помещайте в свертываемую группу элементы, которые требуются часто или являются обязательными

6. Не размещайте свертываемую группы выше обычных групп

[↑ Наверх](#гайд-для-создания-форм-на-1с)

#### Всплывающая группа

Всплывающая группа может использоваться для размещения необязательных или справочных реквизитов, чтобы форма была компактнее

<img src=img/popupGroup.png width=700 border=1>

1. Используйте элемент с осторожностью, так как для пользователя такая группа не является привычным элементом и он может пропустить ее
2. Давайте описание содержащихся значений в заголовке группы, чтобы пользователь мог посмотреть их не открывая
3. Установить Отображение управления = Картинка, чтобы появилась соответствующая пиктограмма у группы. Это позволит пользователю узнавать поведение таких элементов
4. Используйте всплывающую группу как подсказку, на которой можно разместить не только форматированную строку, но и дополнительные реквизиты. Сделайте говорящий заголовок, побуждающий пользователя на него нажать
5. Используйте всплывающую группу как открываемую форму по гиперссылке, для этого установите цвет текста заголовка как у гиперссылки

   <img src=img/popupGroupHyperlink.png width=500 border=1>

6. Не помещайте во всплывающую группу обязательные реквизиты, а также реквизиты, которые часто используются
7. Не экономьте на заголовке у всплывающих групп. Пользователь должен понимать, что ожидать при нажатии на заголовок

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Командная панель

Командную панель можно собрать самостоятельно если требуется добавить свои команды

<img src=img/commandPanel.png width=700>

1. Установите Источник команд - Форма для стандартных команд объекта
2. Установите Источник команд - Глобальные команды командной панели формы для глобальных команд, например Структура подчиненности, Дополнительные сведения и История изменений
3. Для того, чтобы разбить табличную часть на две, следует продублировать стандартные команды формы, при этом отключить их в составе команд формы

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Команды формы

1. Расположите основную кнопку слева вверху в формах на весь экран, например, **Провести и закрыть**

    <img src=img/postAndClose.png width=600 border=1>

2. Расположите основную кнопку справа внизу в формах (модальных) не на весь экран, Например, **ОК**

    <img src=img/okButton.png width=600>

3. Используйте только одну кнопку по умолчанию на форме. Если требуется сделать несколько, например, если действия важные и равнозначные, то этим командам установите оформление как у кнопки по умолчанию: шрифт - Жирный и цвет фона кнопки - Золотой RGB(255, 255, 0)

4. Переназначайте кнопку по умолчанию при переключении страниц, если на форме их несколько

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Шапка формы

1. Располагайте элементы сверху вниз, слева направо в порядке важности
2. Расположите справа поля, которые нужно редко менять:
Например, поле Организация или Подразделение заполняется значениями по умолчанию и не требуют внимания пользователя, поэтому разамещайте их справа.
Проверьте, что они заполняются автоматически или сохраняются предыдущие значения
3. Не стремитесь сделать левую и правую часть симметричной. Главное чтобы слева были важные поля, а справа неважные. Нормально, если с правой стороны будет больше полей, чем с левой
4. Скрывайте поля по Функциональным опциям, например, Организация или Подразделение, чтобы упростить форму
5. Не допускайте, чтобы нижние поля влияли на элементы, находящиеся выше. Например, не размещайте сначала Договор, а потом Контрагента. Пользователь может изменить это поле и не обратить внимание на то, что поменялось выше
6. Не размещайте поля, которые изменяют форму ниже других реквизитов. Расположите условный **Вид операции** самым первым полем

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Подвал формы

1. Расположите в подвале наименее важные реквизиты или справочную информацию в виде итогов

    <img src=img/results.png width=600 border=1>

2. В Бухгалтерии предприятия в формах документов последними реквизитами обычно идут Комментарий и Ответственный

    <img src=img/comment.png width=600 border=1>

[↑ Наверх](#гайд-для-создания-форм-на-1с)

### Условное оформление

Условное оформление используется для визуального выделения данных на основе заданных условий

1. Применяйте одни и те же стили для аналогичных условий, например в динамическом списке новые элементы выделяются жирным
2. Не используйте много различных стилей и цветов
3. Не используйте условное оформление для управления видимостью строк

[↑ Наверх](#гайд-для-создания-форм-на-1с)

## Дополнительные материалы

1. [Стандарты по оформлению форм](https://its.1c.ru/db/v8std#browse:13:-1:11)
2. [Хитрости и советы по созданию форм от Рарус](https://rarus.ru/publications/20220530-ot-ekspertov-hitrosti-po-sozdaniyu-form-1c-532555/)
3. [Контур.Гайды](https://guides.kontur.ru/)
4. Репозиторий [UX-1C:Элементы интерфейса 1С](https://github.com/shch-anna/ux-1c)
5. Алан Купер об интерфейсе. Основы проектирования взаимодействия
6. [Стек технологий для 1С](https://github.com/Oxotka/StackTechnologies1C)

[↑ Наверх](#гайд-для-создания-форм-на-1с)

## Вопросы и пожелания

Добавляйте вопросы и пожелания в [Issues к этому репозиторию](https://github.com/Oxotka/1CDesignGuide/issues). 

При необходимости гайд будет дополняться

[↑ Наверх](#гайд-для-создания-форм-на-1с)

## Благодарность

Подпишитесь на мой [Телеграм канал](https://t.me/AriN1C) или [купите мне кофе](https://boosty.to/1cnik/donate)

[↑ Наверх](#гайд-для-создания-форм-на-1с)

[<img src='https://infostart.ru/bitrix/templates/sandbox_empty/assets/tpl/abo/img/logo.svg'>](https://infostart.ru/1c/articles/2167324/)

Прочитайте и поставьте + этой статье на Инфостарт - [Гайд для создания форм на 1С](https://infostart.ru/1c/articles/2167324/)

[↑ Наверх](#гайд-для-создания-форм-на-1с)