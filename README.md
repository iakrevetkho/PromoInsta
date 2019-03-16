# PromoInsta
Promotion instagram bot, based on InstaPy tools.

## Program algorithm

### 1 стадия. Аналитика аккаунта.

#### Анализ хештегов аккаунта.
Если у аккаунта есть фотографии с хештегами, то записываем их в базу по количеству упоминаний.
Если нет, то просим пользователя ввести теги самому или берем самые популярные из сервисов.

#### Анализ местоположений у профиля и у постов, если есть
Находим самое частое местоположение или местоположение профиля

### 2 стадия. Работа по расширению аккаунта.

#### Общее правило взаимодействия с пользователем

Анализируем профиль человека.
Смотрим последние 5-10 постов (параметр).
Если у этих постов хоть у одного есть необходимых **хэштег** и хоть у одного **местоположение** из списка (если их нет, то одобряем), то **взаимодействуем** с пользователем.

#### Работа с базой конкурентов.
1. Находим публикации по тегам
2. Запоминаем список аккаунтов которые сделали пост, если удовлетворены настройки (количество лайков у поста, количество постов, кол-во подписчиков)
3. Идем по списку подписчиков каждого конкурента
4. По общим правилам лайкаем 3-5 постов пользователя и подписываемся на него

** Анализ базы конкурентов должен происходить периодически, а работа со списком подписчиков конкурентов каждый день

#### Работа с местоположениями.

Лайки и комментирование по местоположениям для привлечения новых клиентов, которые находятся в той же локации.

### 3 стадия. Работа с операционкой аккаунта.

#### Автоответ на комментарии и лайк.
Определение настроения сообщения и если оно позитивное, то отвечаем и лайкаем, в противном случае нет.
Сообщение переводится на английский и лайкается.

#### Аналитика продвижения.
Расчет конверсии, времени подписки и прочей аналитики.





# Functions

## Set filtering posts location by list
Set locations list for filtering

```python
session.set_locations(['Moscow', 'Moscow, Russia'])
```

Inside function check_link each post checks if location (if exist) in list, else post ignored