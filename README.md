Сайт рецептов.
БАС2101 Рыков Поляков Кубышев
=====

# Таблица "Пользователи"
Данные пользователей для входа и уровень доступа
Уровень доступа представляет собой целочисленное значение, разрешение на чтение, запись, уровень доступа к репозиторию ресурсов и административные функции обозначаются побитово

# Таблица "Рецепты"
Включает в себя связь по id с таблицей "пользователи"
Содержит пользовательский тип "Рецепт"

# Таблица "Настройки"
Не критичные пользовательские настройки (темная тема, язык)

Настройки <=====> Пользователи - один к одному

Пользователи <=====> Рецепты - один к многим

Сервис старается максимально оградить пользователя от создания неоднозначных структур в рецепте, рецепт составляется  из блоков "Ингредиентов" и блоков "Действий", имеется возможность создавать пользовательские ресурсы.

По умолчанию, только что зарегистрированный пользователь имеет доступ только на чтение.

# Класс "Рецепт" RecipeEntry
Содержит в себе общие сведения о рецепте и массив с объектами типа "Шаг"(Step)

# Класс "Шаг" Step
Содержит в себе общие сведения о шаге(фото, текст), может ссылаться на другой рецепт.

### Про принцип DRY и зависимости в рецептах:
Если при приготовлении блюда требуется соус, то приготовления соуса выносится в отдельный рецепт, а изначальный рецепт ссылается на рецепт соуса. 
Таким образом рецепты имеют зависимости.
Использование такого подхода позволяет использовать один рецепт в любых других рецептах.
