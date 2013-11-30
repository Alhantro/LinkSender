LinkSender
===============================================================================================================================
Программа, которая позволяет легко поделиться ссылкой на ресурс в интернете с вашими друзьями.
===============================================================================================================================
1)Code  Conventions
2)Style Conventions
===============================================================================================================================

Code  Conventions
Общие правила

Все отклонения от правил стандарта должны быть подробно прокомментированы в коде.
Компилятор стоит настроить так, чтобы «char» реализовывался как «unsigned char».

Классы: общие правила
Экземпляры класса стоит определять напрямую конструктором, а не копирующим конструктором через присвоение.
Для определения конструктора присвоения используйте атомарную не генерирующую исключения операцию «swap».
Оператор присвоения должен быть реализован корректно относительно самоприсвоения, и консистентно относительно присвоения по умолчанию.
Не объявляйте методы класса инлайнами, вместо этого определяйте их в теле класса.
Все методы, которые не изменяют видимое извне состояние объекта, должны быть определены константными.
Обеспечьте оператор вывода в поток "<<" для каждого класса

Классы: конструкторы и деструкторы
Записывайте члены класса в списке инициализации в том же порядке, в каком они объявляются.
Определяйте все конструкторы с одним аргументом как «explicit» (за исключением копирующего конструктора).
Деструкторы должны освобождать все ресурсы, принадлежащие объекту.
Не объявляйте конструкторы и деструкторы инлайнами.

Классы: ООП
Не возвращайте неконстантные ссылки на члены класса из константных функций.
Избегайте использования дружественных классов и методов, если только архитектура не требует их явно.

Классы: перегрузка операторов
Объявляйте перегруженные операторы вне класса, чтобы для них работала конвенция приведения по левому операнду.
Убедитесь, что перегруженные бинарные операторы сохраняют ожидаемое поведение.

Поток управления
Каждый блок примитива управления потоком («if», «else», «while», «for», «do», «switch») должен заключаться в скобки, даже если он содержит только одну строку, или не содержит ничего вовсе.
В булевских выражениях («if», «for», «while», «do» и первом операнде тернарного оператора "?") всегда записывайте равенство и неравенство в явном виде.
Каждый непустой блок выражения «switch» должен заканчиваться командой «break».
Не модифицируйте переменные контроля цикла «for» в теле цикла.
Не модифицируйте переменные контроля цикла «while» и «do» в теле цикла более чем один раз.
Переменная контроля цикла «for» должна сравниваться с константой, а не функцией или выражением.
Определяйте в явном виде все возможные ветви условного оператора.
Переменные контроля цикла «for» следует объявлять непосредственно внутри «for», а не использовать внешние переменные.

Объявления и определения
Не затеняйте объявления в внутренних областях видимости.
Избегайте использования глобальных переменных.
Используйте декларации «using», или обозначайте пространство имен явно, избегайте директив «using».
Директивы «using» допускается использовать только в главном исходном файле и только после всех директив «include».
Избегайте использования «auto» и «register».
Все идентификаторы должны быть уникальны.
Не используйте пары символов «l» (буква «эль») и «1» (один), а также «O» (буква «о») и «0» (ноль) в одном идентификаторе.
Объявляете каждую переменную в отдельной строке отдельным объявлением. Если объявление не самоочевидно, добавляйте соответствующий комментарий.
Инициализируйте каждый объект при определении. Никогда не используйте объект до первого присвоения ему значения.
Определяйте переменные как можно ближе к контексту использования.
Используйте типы классов или определения типов через «typedef» для обособления типа числа.
Объявляйте только одно имя в каждом «typedef».
Используйте «const» везде, где это возможно
Присоединяйте "*" и "&" к типу (а не к имени переменных) в объявлениях и определениях.
Предпочитайте знаковые типы беззнаковым.

Выражения
Используйте символические имена вместо конкретных значений в коде. Избегайте «magic numbers» (за исключением "\0", 0, 1, true, false и однократных строковых литералов).
Не полагайтесь на определенный порядок вычисления операндов выражения.
Используйте скобки дополнительно для раскрытия сути выражения.
Всегда игнорируйте результат оператора присвоения
При сравнении переменной и константы всегда размещайте константу слева.
Не допускайте сторонних эффектов в правой части операторов "&&", "||", а также в операндах «sizeof» и «typeid».
===============================================================================================================================

Style Conventions
Имена
Давайте локальным переменным короткие, а глобальным - длинные и осмысленные имена.
Избегайте повторения переменных с одинаковым именем, но разным назначением в программе.
Имена методов начинайте с маленькой буквы, следующее слово начинайте с большой (camelCase)
Имена переменных начинайте с мальнькой буквы и используйте нижнее подчеркивание, для разделения слов(my_var)
Имена приватных членов класса начинайте с символа подчеркивания (_private_member)
Название функции должно четко отражать ее цель. Имя должно содержать глагол в активном залоге (#setName())
Классы всегда должны начинаться с заглавной буквы

Отступы
Делайте отступ перед скобками в управляющих конструкциях.
Делайте отступ перед открывающей фигурной скобкой.
Отделяйте символом перевода строки каждую инструкцию.
Открывающую скобку оставляйте на той же строке, что и оператор. Закрывающую переносите на следующую строку (C-style)
Отделяйте логические блоки и методы символом перевода строки
Не допускайте более двух символов перевода строки в коде
Окружайте бинарные операторы пробелами (c = a + b;)
Отделяйте комментарии пробелом от их объявлений (// some comment.)

Функции
Используйте единообразие стиля в именовании переменных и функция, последовательности передачи параметров.

Комментарии
Отдавайте придпочтение комментариям в стиле C++ (//)
Комментируйте участки кода, которые кажутся неочевидными.
Комментируйте особенности вашей функции
Комментарии, помещенные в одну строку с инструкцией начинайте с маленькой буквы, завершайте точкой/(// some comment.)
Всегда комментируйте функции и переменные перед их объявлением или реализацией. а не после.
Комментарий, написанный на новой строке начинается с большой буквы и заканчивается символом двоеточие. (// Some comment:)

