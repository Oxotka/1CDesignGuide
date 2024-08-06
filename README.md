[![OpenYellow](https://img.shields.io/endpoint?url=https://openyellow.neocities.org/badges/4/799152816.json)](https://openyellow.notion.site/openyellow/24727888daa641af95514b46bee4d6f2?p=27e2878921a84be3805410324117c660&amp;pm=s) [![Static Badge](https://img.shields.io/badge/my%20telegram-channel-green)](https://t.me/AriN1C) [![Static Badge](https://img.shields.io/badge/infostart-profile-green)](http://infostart.ru/profile/237528/)

# Гайд для создания форм на 1С

**Дополнительные материалы:**

1. [Стандарты по оформлению форм](https://its.1c.ru/db/v8std#browse:13:-1:11)
2. [Хитрости и советы по созданию форм от Рарус](https://rarus.ru/publications/20220530-ot-ekspertov-hitrosti-po-sozdaniyu-form-1c-532555/)
3. [Контур.Гайды](https://guides.kontur.ru/)
4. Алан Купер об интерфейсе. Основы проектирования взаимодействия

**Дизайн:**

- [Гайд для создания форм на 1С](#гайд-для-создания-форм-на-1с)
  - [Элементы формы](#элементы-формы)
    - [Декорация](#декорация)
      - [Декорация-надпись](#декорация-надпись)
      - [Декорация-картинка](#декорация-картинка)
    - [Поле ввода](#поле-ввода)
    - [Флажок](#флажок)
    - [Переключатель](#переключатель)
    - [Тумблер](#тумблер)
    - [Выключатель (Тогл, Свитчер)](#выключатель-тогл-свитчер)
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
    - [Сохранение размера формы](#сохранение-размера-формы)
  - [Благодарность](#благодарность)

## Элементы формы

### Декорация

Самый простой элемент дизайна форм. Можно вывести любой текст

<img src=img/usualLabel.png width=500>

#### Декорация-надпись

<img src=img/formatString.png width=500>

1. Используется как подсказка на форме. В этом случае часто используют Форматированную строку, чтобы добавить гиперссылки и оформление
2. Может использоваться как заголовок у сложных полей
3. Есть текст из одного предложения, то в конце точка не ставится
4. Не следует использовать декорацию если она, не выполняет полезное действие
5. Не следует использовать для установки заголовки простых полей. В этом случае не срабатывает автофокус на поле и часто забывают поставить двоеточие в заголовке поля
6. Не следует использовать для выравнивания элементов. Лучше использовать для этого свойства [Групп](#группы)


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

#### Декорация-картинка

 <img src=img/pictureLabel.png width=500>

1. Картинка может использовать для иллюстрации или чтобы обратить внимание пользователя
2. Картинка может быть и в составе форматированной строки, и отдельным элементом


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Поле ввода

Поле ввода - это базовый элемент для ввода значений

 <img src=img/inputField.png width=500 border=1>

1. Если в поле ввода предусмотрено удаление или пустое значение, то нужно добавить кнопку Очистки (x). Исключение: Отборы на формах, там используется флажок
2. Для строковых полей ввода иногда следует предусмотреть кнопку выбора, например, выбор Пути к файлу или например выбор Наименования
3. Для списка выбора ширина поля должна вмешать самое длинное значение
4. Не всегда нужно использовать заголовок поля ввода. Например, в шапке отчета мы не пишем у поля Организация заголовок, так как пользователи знают свою организацию и понять что в этом поле указано по значению

<details><summary>Как выглядит В ЕДТ</summary>

![Организация](img/organization.png)

</details>

4. В случае если заголовок не указываем, то обязательно должна быть подсказка ввода. То есть для Организаций в отчете следует писать: По всем организациям. Таким образом, показываем, что сейчас символизирует собой этой поле


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Флажок

Флажок используем для включения или выключения какой-либо опции (у него два состояния)

<img src=img/checkboxTitle.png width=450 border=1>

1. У флажка заголовок устанавливаем справа. Здесь следует отойти от умолчания платформы

    <details><summary>Как выглядит В ЕДТ</summary>

    ![Заголовок флажка](img/checkbox.png)

    </details>

2. Зона действия флажка, с точки зрения интерфейса, небольшая или отсутствует. Например, при включении флажка можно включить доступность соседнего реквизита или гиперссылки. В случае если требуется влиять на форму сильнее, то лучше использовать [Выключатель](#выключатель-тогл-свитчер) или [Переключатель](#переключатель)
3. Флажок следует использовать для простой опции, в которой понятно, что означают оба состояния. Если из названия сложно понять действие флажка, то можно добавить подсказку снизу
4. Не следует использовать флажок для сложных опций, в которых не понятно оба состояния. В этом случае лучше использовать [Переключатель](#переключатель)
5. Не следует в заголовке флажка использовать отрицательные формулировки, потому что пользователю потребуется дополнительное усилие, чтобы понять выключенный флажок, например, «Не Не проводить документ при записи»


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Переключатель

Переключатель используется для выбора одного значения из нескольких перечисленных

<img src=img/radiobuttons.png width=500 border=1>

1. Переключатель лучше использовать когда значений немного - от 2 до 5, если значений больше, то используется [Поле ввода](#поле-ввода) по списком значений
2. Переключатель действует на то, что находится справа и под ним
3. Выбранное значение по умолчанию должно идти первым в списке
4. Для сложных опций рекомендуется добавлять подсказки к значениям переключателя.

    Для этого создайте два элемента с путем к одному реквизиту. В этом случае у каждого элемента можно сделать свою подсказку

    <details><summary>Как выглядит в конфигураторе</summary>
    <img src=img/radiobuttonsWithHints.png width=500 border=1>
    </details>

5. В значениях переключателя не должно быть повторяющихся текстов, их лучше вынести в заголовок


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Тумблер

Тумблер используется для выбора одного значения из нескольких перечисленных. Аналогичен [Переключателю](#переключатель)

<img src=img/switcher.png width=600 border=1>

1. Тумблер выглядит как кнопки, поэтому лучше использовать его, если от значения перестраивается форма под ним, выполняется какое-то действие
2. Тумблер лучше использовать для 3-5 значений
3. Тумблер выглядит компактнее, чем Переключатель и подходит для не слишком длинных значений
4. Не следует в элементах использовать повторяющиеся слова, лучше вынести их в заголовок
5. Не следует использовать тумблер для 2 значений - не ясно какой пункт выбран


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Выключатель (Тогл, Свитчер)

Выключатель переключает состояние. Например, включает или выключает какую-либо опцию. Это вид флажка и к нему применяются правила флажка.

Выключатель заимствован из мобильных операционных систем, где он используется для включения и выключения настроек

<img src=img/toggle.png width=350 border=1>

1. При переключении состояния выключателя действия происходит сразу, то есть не нужны дополнительные подтверждения
2. Выключатель ассоциируется с большим влиянием, чем флажок. То есть при изменении состояния действие на форму может быть более обширным
3. Не следует использовать на одной странице больше 2-3 выключателей


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)


### Гиперссылки

Гиперссылка используется для перехода к другой форме. Пользователю привычно, что по гиперссылке он куда-то перейдет или откроется новая форма, то есть будет потерян фокус с основной формой

1. Используется для открытие подчиненных и служебных форм. Например, настройка НДС

<img src=img/hyperlink.png width=300 border=1>

2. Гиперссылка должна иметь осмысленное название и достаточно длинным, чтобы в нее можно было нажать
3. С помощью гиперссылки не следует выполнять действия на форме. Для этого следует использовать [Кнопки](#кнопка)
4. Из гиперссылки должно быть понятно, куда она ведет
5. Не следует в названии использовать слова "здесь" или "тут"
6. Не следует использовать две ссылки подряд - трудно заменить переход между двумя ссылками
7. Не следует менять цвет гиперссылки, за исключением ссылок с предупреждением


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Кнопка

1. Кнопка должна выполнять действие
2. Допускается использовать кнопку Без фигуры для команд, которые не рекомендуется выполнять или когда кнопок слишком много
Подробнее про [отображение кнопок без фигур](https://t.me/AriN1C/46)
3. Кнопка с пометкой используется для команды, связанной со строкой списка (табличная часть или динамический список), например "Использовать как основной"
4. Не следует использовать кнопку для перехода к другой форме, для этого следует использовать [Гиперссылку](#гиперссылки)

<img src=img/button.png width=150 border=1>


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Табличная часть

1. В табличной части должен быть заголовок в 1 строку. При необходимости вывести сложный заголовок следует рассмотреть возможность выводить эти значения в самой таблице. Например, см. Корректировка реализации
2. В случае если табличная часть из одной колонки, то шапка не нужна. В этом случае лучше описать декорацией содержание табличной части, если это требуется
3. В табличной части последней колонкой должна идти пустая колонка, чтобы проще было управлять шириной табличной части. У этой колонки следут отключить заголовок, включить флаг "Только просмотр" и установить "Растягивать по горизонтали"
4. Заголовок колонки табличной части следует прижимать к значению, например, для Числа следует прижимать вправо, а для Строка или Ссылка оставлять по умолчанию слева

Еще некоторые пункты оформления описаны в стандарте для проектирования интерфейсов - <https://its.1c.ru/db/v8std/content/717/hdoc>

<img src=img/table.png width=800 border=1>


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Диалоговое окно

Диалоговое окно открывается для вопроса или предупреждения пользователю. Это блокирующее сообщение, которое требует обязательного внимания пользователя.
Обычно выводится для необратимых действий, например, очистка табличной части или установка особого режима работы

<img src=img/dialog.png width=600>

1. Стоит уделить особое внимание тексту в диалоговом окне. Из текста должно быть понятно, что требуется от пользователя. Должен быть четкий вопрос с однозначным ответом
2. Утвердительная кнопка должна однозначно говорить о том, что будет выполнено. В идеале должна повторять действие, которое запрашивается у пользователя
3. Кнопка закрытия диалогового окна (крестик справа вверху) должене обрабатываться. Для этого одна из команд диалогового окна должна быть Отмена. Для этого стоит добавить свои кнопки диалогового окна

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


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Подсказка и расширенная подсказка

У большинства элементов есть свойство Подсказка, которая выводится в зависимости от свойства Отображение подсказки.
Подсказка - это обычная строка, но можно включить Расширенную подсказку, чтобы использовать форматированную строку. Для этого на элементе формы следует нажать на правую кнопку мыши и выбрать пункт Показать расширенную подсказку

1. Для разовых подсказок хорошо подходит отображение через кнопку. Например, если пользователь видит новый ему элемент и сомневается, что с ним делать. В этом случае ему достаточно один раз посмотреть подсказку по кнопке, чтобы понять, что делать. Позже он сможет вернуться к этой подсказке, если потребуется
    
    <img src=img/buttonHint.png width=700 border=1>

2. Если форма используется не часто, то можно расположить подсказку сверху о всей форме, чтобы у пользователя она всегда была перед глазами. Например, если это форма с настройками каких-то правил. В этом случае пользователь при открытии формы сразу видит, что нужно сделать

    <img src=img/underHint.png width=700 border=1>

3. Для некоторых сложных элементов стоит сделать подсказку снизу, чтобы объяснить, что этот реквизит означает. Важно давать подсказки на важные элементы формы, чтобы подчеркнуть их важность

4. Для акцентирования внимания на конкретный реквизит допустимо использовать различные средства выделения, например, желтый фон или картинки

5. Подсказок много не бывает, но они не должны быть навязчивыми


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

## Компоновка формы

### Группы

Группы используются для объединения элементов вместе. Группы позволяют управлять расположением и выводом элементов

#### Обычная группа

1. В большинстве случае не следует отображать заголовок у группы
2. Не следует в заголовке группы писать слово "Группа" (по умолчанию платформа его добавляет - следует убрать)
3. Не следует оставлять бессмысленные подсказки в группе, так как они выводится при удержании курсора над группой (по умолчанию платформа добавляет - следует убрать)
4. Лучше избегать Расположение - Горизонтально, если возможно. Исходить следует из минимально допустимого расширения 1280х768 px
5. Типы выделения обычной группы. Сильное выделение - добавляется полоса и отступ у подчиненных реквизитов, Обычное выделение и Слабое выделение - крупный заголовок

   <img src=img/highlightGroup.png width=500 border=1>

6. Обычное выделение имеет больший отступ вокруг себя. [Подробнее о слабом и обычном отображении групп](https://t.me/Aripovn/31)

   <img src=img/representationGroup.gif width=500>

7. Для выравнивая элементов в подчиненных группах следует использовать свойство - **Сквозное выравнивание**. Это свойство позволяет выравнять элементы, которые находятся в подчиненных группах

    <details><summary>Как выглядит В ЕДТ</summary>
        <img src=img/endToEndAlignment.png width=500>
    </details>

8. Для прижатия элементов к одному из краев следует использовать свойство - **Выравнивание элементов и заголовков**

    <details><summary>Как выглядит В ЕДТ</summary>
        <img src=img/aligment.png width=500>
    </details>


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

#### Свертываемая группа

Свертываемая группа позволяет скрыть реквизиты внутри сворачиваемого блока

<img src=img/collapsibleGroupTitle.png width=500 border=1>  

1. Свертываемая группа используется, чтобы скрыть элементы - это делаем форму компактнее и удобнее для работы.
Также смотри стандарт - [Оформление групп разделов с настройками и справочниками](https://its.1c.ru/db/v8std/content/753/hdoc)

2. В заголовке свертываемой группы с реквизитами следует давать описание содержашихся значений, например, см. Банковский счет и Адрес:

    <img src=img/titleOnGroup.png width=700 border=1>

   В случае если в группе находятся только команды или гиперссылки (см. пример в Администрирование в БСП), то заголовок свернутой группы необязательно формировать. В этом случае мы упрощаем навигацию по форме для пользователя

3. У свертываемой группы с реквизитами следует снять флаг "Отображать отступ слева", чтобы элементы была вровень с остальными реквизитами формы

    <details><summary>Как выглядит В ЕДТ</summary>
        ![Свертываемая группа](img/collapsibleGroup.png)
    </details>

4. Лайфхак для программного управлением свойства группы Свернута. Управлять этим свойством программно нельзя, но можно создать две группы с одинаковыми реквизитами, одна по умолчанию свернута, а другая по умолчанию развернута. ПриСозданииНаСервере следует проверить какую группу показать пользователю.

5. Не следует помещать в свертываемую группу элементы, которые требуются часто или являются обязательными

6. Не следует размещать свертываемую группы выше обычных групп


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

#### Всплывающая группа

Всплывающая группа может использоваться для размещения необязательных или справочных реквизитов, чтобы форма была компактнее

<img src=img/popupGroup.png width=700 border=1>

1. Для пользователя такая группа не является привычным элементом и он может пропустить ее. Поэтому следует использовать элемент с осторожностью
2. В случае если реквизиты заполнены, то следует давать описание содержащихся значений в заголовке группы, чтобы пользователь мог посмотреть их не открывая
3. У группы следует установить Отображение управления = Картинка, чтобы появилась соответствующая пиктограмма. Это позволит пользователю узнавать поведение таких элементов
4. Всплывающую группу можно использовать как группу с подсказкой, на которой можно разместить не только форматированную строку, но и дополнительные реквизиты. Важно в этом случае сделать говорящий заголовок, побуждающий пользователя на него нажать
5. Всплывающую группу можно использовать как открываемую форму по гиперссылке, в этом случае следует устновить цвет текста заголовка как у гиперссылки

   <img src=img/popupGroupHyperlink.png width=500 border=1>

6. Не следует помещать во всплывающую группу обязательные реквизиты, а также реквизиты, которые часто используются
7. Не следует экономить на заголовке у всплывающих групп. Пользователь должен понимать что ожидать при нажатии на заголовок


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)


### Командная панель

Командную панель можно собрать самостоятельно если требуется добавить свои команды

1. Для стандартных команд формы у группы следует устанавить Источник команд - Форма
2. Для глобальных команд (структура подчиненности, дополнительные сведения и история изменений) у группы следует установить Источник команд - Глобальные команды командной панели формы

<img src=img/commandPanel.png width=700>


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Команды формы

1. В формах на весь экран основная кнопка обычно располагается слева вверху, например, **Провести и закрыть**

    <img src=img/postAndClose.png width=600>

2. В формах (модальных) не на весь экран основная кнопка располагается справа внизу, Например, **ОК**

    <img src=img/okButton.png width=600>

3. На форме должна быть одна кнопка по умолчанию. В случае если требуется сделать несколько, например, если действия важные и равнозначные, то этим командам следует установить оформление как у кнопки по умолчанию: шрифт - Жирный и цвет фона кнопки - Золотой RGB(255, 255, 0)

4. Если на форме несколько страниц, то кнопку по умолчанию следует переназначать при переключении страниц


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Шапка формы

Элементы располагаем сверху вниз, слева направо в порядке важности

1. Поля, которые нужно редко менять располагаем справа:
Например, поле Организация или Подразделение как правило заполняется значениями по умолчанию и не требуют внимания пользователя, поэтому располагаем их справа.
Для таких полей обязательно проверить, что они заполняются автоматически или сохраняются предыдущие значения

2. Не следует стремится сделать левую и правую часть симметричной. Гораздо важнее чтобы слева были важные поля, а справа неважные. Вполне вероятно, что с правой стороны будет больше полей, чем с левой

3. Некоторые поля могут скрываться по Функциональным опциями, например, Организация или Подразделение

4. Важно, не допустить ситуации, что поля ниже влияют на поля находящиеся выше. Например, не следует размещать сначала Договор, а потом Контрагента. Иначе пользователь может изменить это поле и не обратит внимание на то, что поменялось выше

5. Не следует размещать поля, которые изменяют форму ниже других реквизитов. То есть условный **Вид операции** должен идти самым первым полем


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Подвал формы

В подвале располагается наименее важные реквизиты. Также там может быть справочная информация в виде итогов

<img src=img/results.png width=600 border=1>

В Бухгалтерии предприятия в формах документов последними реквизитами обычно идут Комментарий и Ответственный

<img src=img/comment.png width=600 border=1>

[⬆️ Наверх](#гайд-для-создания-форм-на-1с)

### Сохранение размера формы

Для сохранения размера и положения окна следует испольпользовать свойство **КлючСохраненияПоложенияОкна**

Не актуально в платформе 8.3.23 и старше

Подробнее про [управление размером формы](https://t.me/AriN1C/45)

```BSL
&НаКлиентеНаСервереБезКонтекста 
Процедура УправлениеФормой(Форма, Шаг) 
  
 Элементы = Форма.Элементы; 
  
 Если Шаг = 1 Тогда  
   
  Элементы.ГруппаСтраницы.ТекущаяСтраница = Элементы.СтраницаВход; 
  Элементы.СтраницаВход.Видимость = Истина; 
  Элементы.СтраницаРеквизиты.Видимость = Ложь;
                Элементы.СтраницаУспешно.Видимость = Ложь; 
   
 ИначеЕсли Шаг = 2 Тогда 
   
  Элементы.ГруппаСтраницы.ТекущаяСтраница = Элементы.СтраницаРеквизиты; 
  Элементы.СтраницаВход.Видимость = Ложь; 
  Элементы.СтраницаРеквизиты.Видимость = Истина;
                Элементы.СтраницаУспешно.Видимость = Ложь; 
 Иначе 
   
  Элементы.ГруппаСтраницы.ТекущаяСтраница = Элементы.СтраницаУспешно; 
  Элементы.СтраницаВход.Видимость = Ложь; 
  Элементы.СтраницаРеквизиты.Видимость = Ложь;
                Элементы.СтраницаУспешно.Видимость = Истина; 
 
 КонецЕсли; 
 
 Форма.КлючСохраненияПоложенияОкна = СтрШаблон("СостояниеФормыШаг%", Шаг); 
  
КонецПроцедуры
```


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)


## Благодарность

Если статья была полезная или просто хотите поддержать автора,
то можете подписаться на мой [Телеграм](https://t.me/AriN1C) или [купить мне кофе](https://boosty.to/1cnik/donate)


[⬆️ Наверх](#гайд-для-создания-форм-на-1с)