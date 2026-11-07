# Глоссарий локализации Frappe / ERPNext / HRMS (ru)

Глоссарий создан заново при переводе `frappe/ru.po` (Frappe Framework v16). Все термины пока в статусе «на утверждение».

## Сквозные правила (на утверждение)

- **Буква «ё»** не используется (как в 1С): «Отчет», «Проведен», «Удален».
- **Проведение документов.** Submit → «Провести», Submitted → «Проведен», Cancel → «Отменить», Cancelled → «Отменен», Amend → «Исправить», Amended From → «Исправлено из». В веб-формах и диалогах Submit → «Отправить».
- **Кнопки и лейблы** — инфинитив или существительное без точки: «Сохранить», «Добавить строку». Сообщения — полные предложения.
- **Статусы** согласуются с родом документа, если он известен. Если нет, используется средний род: «Отменено», «Завершено».
- **DocType** в интерфейсе — «Тип документа». Служебные имена (`DocType`, `fieldname`, `name`) в коде и кавычках не переводятся.
- **Email** — «Эл. почта» в коротких лейблах, «электронная почта» / «письмо» в предложениях. Email (глагол) → «Отправить по эл. почте».
- **Названия продуктов и технологий** не переводятся: Frappe, Google, Dropbox, OAuth, LDAP, Jinja, Markdown, JSON, CSV, Redis, MariaDB, PostgreSQL.
- **Кавычки** — «ёлочки»; прямые кавычки только в коде и экранированных значениях.
- **Общие msgid без контекста** (Submit, Save, Delete, Create, Edit, Amend, Cancel, Execute, Attach, Share) переводятся **глаголом**: один и тот же msgid служит и кнопкой формы, и подписью права доступа. Существительное («Проведение», «Сохранение») — только при наличии `msgctxt`, где это явно процесс (например, freeze-сообщение «Saving»).
- **Permission / Permissions** — «разрешение / разрешения» в тексте и лейблах; «Права доступа» — только заголовок раздела Permissions и производные («Менеджер прав ролей», «Права ролей»).
- **Reference …** (Reference Document, Reference DocType) — «… основания / документ-основание» (как в 1С), а не «ссылочный документ».
- **Сокращения чисел** (number_systems.js): K → «тыс.», M → «млн», B → «млрд», T → «трлн». Индийские Lakh/Crore/Arab/Kharab (L, Cr, Ar, Kh) не переводятся.
- **Сокращения времени** (pretty_date.js): {0} m → «{0} мин», {0} h → «{0} ч», {0} d → «{0} д», {0} w → «{0} нед.», {0} M → «{0} мес.», {0} y → «{0} г.».
- **Действия в ленте** («{0} created this document») — прошедшее время с родовой парой: «создал(а)», «провел(а)», «изменил(а)».
- **Технические значения** (имена событий webhook `on_submit`, очереди RQ `default/short/long`, форматы дат `dd-mm-yyyy`, редакторы `vim/emacs`) не переводятся.

## Новые термины (на утверждение)

| English | Русский | Контекст (модуль / msgctxt) | Пример msgid |
|---|---|---|---|
| DocType | Тип документа | core | Create a new DocType |
| Child Table | Дочерняя таблица | core | Child Table |
| Single (DocType) | Одиночный | core / DocType | Is Single |
| Submittable | Проводимый | core / DocType | Is Submittable |
| Document | Документ | общее | Document Name |
| Field | Поле | core | Field Name |
| Fieldname | Имя поля | core | Fieldname |
| Fieldtype | Тип поля | core | Fieldtype |
| Label | Подпись | core | Label |
| Options (field) | Параметры | core | Options |
| Mandatory | Обязательное | core | Mandatory Depends On |
| Read Only | Только чтение | core | Read Only |
| Hidden | Скрытое | core | Hidden |
| Default | По умолчанию | core | Default Value |
| Depends On | Зависит от | core | Depends On |
| Section Break | Разрыв раздела | core / fieldtype | Section Break |
| Column Break | Разрыв колонки | core / fieldtype | Column Break |
| Tab Break | Разрыв вкладки | core / fieldtype | Tab Break |
| Row | Строка | общее | Add Row |
| Column | Колонка | общее | Add Column |
| Naming Series | Серия нумерации | core | Naming Series |
| Autoname | Автоименование | core | Auto Name |
| Customize Form | Настройка формы | custom | Customize Form |
| Custom Field | Пользовательское поле | custom | Custom Field |
| Property Setter | Установщик свойств | custom | Property Setter |
| Module | Модуль | core | Module Def |
| Module Def | Определение модуля | core | Module Def |
| App | Приложение | общее | Installed Apps |
| Workspace | Рабочая область | desk | Workspace |
| Desk | Рабочий стол | desk | Desk User |
| Sidebar | Боковая панель | desk | Sidebar |
| Shortcut | Ярлык | desk / Workspace | Shortcut |
| Dashboard | Панель мониторинга | desk | Dashboard Chart |
| Dashboard Chart | Диаграмма | desk | Dashboard Chart |
| Number Card | Числовая карточка | desk | Number Card |
| Kanban Board | Канбан-доска | desk | Kanban Board |
| List View | Список | desk | List View Settings |
| Report View | Представление отчета | desk | Report View |
| Report Builder | Конструктор отчетов | desk | Report Builder |
| Script Report | Отчет-скрипт | core / Report | Script Report |
| Query Report | Отчет-запрос | core / Report | Query Report |
| Prepared Report | Подготовленный отчет | core | Prepared Report |
| Filter | Фильтр | общее | Add Filter |
| Group By | Группировать по | desk | Group By |
| Sort | Сортировка | desk | Sort Order |
| Print Format | Печатная форма | printing | Print Format |
| Print Format Builder | Конструктор печатных форм | printing | Print Format Builder |
| Letter Head | Фирменный бланк | printing | Letter Head |
| Print | Печать / Печать (кнопка) | printing | Print |
| Submit | Провести | документ | Submit |
| Submitted | Проведен | документ | Submitted |
| Cancel | Отменить / Отмена (вторичная кнопка диалога) | документ / диалог | Cancel |
| Cancelled | Отменен | документ | Cancelled |
| Amend | Исправить | документ | Amend |
| Draft | Черновик | документ | Draft |
| Discard | Отменить | форма | Discard |
| Duplicate | Дублировать | форма | Duplicate |
| Rename | Переименовать | форма | Rename |
| Role | Роль | permissions | Role Profile |
| Role Profile | Профиль ролей | permissions | Role Profile |
| Permission | Разрешение | permissions | User Permission |
| Permissions | Права доступа | permissions | Role Permissions Manager |
| Permission Level | Уровень доступа | permissions | Perm Level |
| User Permission | Разрешение пользователя | permissions | User Permission |
| Role Permissions Manager | Менеджер прав ролей | permissions | Role Permissions Manager |
| Share | Поделиться / Совместный доступ | desk | Share With |
| Assign To | Назначить | desk | Assign To |
| Assignment | Назначение | desk | Assignment Rule |
| Assigned To | Назначено | desk | Assigned To |
| ToDo | Задача | desk | ToDo |
| Attachment | Вложение | общее | Attachments |
| Attach | Прикрепить | общее | Attach File |
| Comment | Комментарий | общее | Add a comment |
| Tag | Тег | общее | Add Tags |
| Like | Нравится | общее | Liked By |
| Follow | Отслеживать | desk | Follow |
| Owner | Владелец | общее | Owner |
| Created On | Дата создания | общее | Created On |
| Modified / Last Updated | Изменено | общее | Last Modified |
| Modified By | Изменил | общее | Modified By |
| User | Пользователь | core | User |
| System User | Системный пользователь | core / User | System User |
| Website User | Пользователь сайта | core / User | Website User |
| Login | Вход / Войти (кнопка) | auth | Login |
| Logout | Выйти | auth | Logout |
| Session | Сеанс | auth | Session Expiry |
| Two Factor Authentication | Двухфакторная аутентификация | auth | Enable Two Factor Auth |
| OTP | Одноразовый пароль | auth | OTP App |
| API Key | Ключ API | integrations | API Key |
| API Secret | Секрет API | integrations | API Secret |
| Token | Токен | integrations | Access Token |
| Webhook | Вебхук | integrations | Webhook |
| Integration | Интеграция | integrations | Integrations |
| Social Login | Вход через соцсети | integrations | Social Login Key |
| Email | Эл. почта | email | Email |
| Email Account | Учетная запись эл. почты | email | Email Account |
| Email Domain | Почтовый домен | email | Email Domain |
| Email Queue | Очередь эл. почты | email | Email Queue |
| Email Template | Шаблон письма | email | Email Template |
| Inbox | Входящие | email | Inbox |
| Unsubscribe | Отписаться | email | Unsubscribe |
| Newsletter | Рассылка | email | Newsletter |
| Notification | Уведомление | общее | Notification Settings |
| Auto Repeat | Автоповтор | automation | Auto Repeat |
| Assignment Rule | Правило назначения | automation | Assignment Rule |
| Workflow | Рабочий процесс | workflow | Workflow |
| Workflow State | Состояние рабочего процесса | workflow | Workflow State |
| Workflow Action | Действие рабочего процесса | workflow | Workflow Action |
| Transition | Переход | workflow | Transition Rules |
| Scheduler | Планировщик | core | Scheduler Status |
| Scheduled Job | Запланированное задание | core | Scheduled Job Type |
| Background Job | Фоновое задание | core | Background Jobs |
| Queue | Очередь | core | Queued |
| Server Script | Серверный скрипт | core | Server Script |
| Client Script | Клиентский скрипт | custom | Client Script |
| Log | Журнал | core | Error Log |
| Error Log | Журнал ошибок | core | Error Log |
| Activity Log | Журнал активности | core | Activity Log |
| Access Log | Журнал доступа | core | Access Log |
| Version | Версия | core | Version |
| Data Import | Импорт данных | core | Data Import |
| Data Export | Экспорт данных | core | Data Export |
| Backup | Резервная копия | core | Download Backups |
| Translation | Перевод | core | Translation |
| Language | Язык | core | Language |
| Currency | Валюта | geo | Currency |
| Country | Страна | geo | Country |
| Address | Адрес | contacts | Address Template |
| Contact | Контакт | contacts | Contact |
| Website | Сайт | website | Website Settings |
| Web Page | Веб-страница | website | Web Page |
| Web Form | Веб-форма | website | Web Form |
| Web Template | Веб-шаблон | website | Web Template |
| Blog Post | Публикация блога | website | Blog Post |
| Blogger | Автор блога | website | Blogger |
| Portal | Портал | website | Portal Settings |
| Route | Маршрут | website | Route |
| Help Article | Статья справки | website | Help Article |
| Energy Point | Балл активности | social | Energy Point Log |
| Event | Событие | desk | Event |
| Note | Заметка | desk | Note |
| Setup Wizard | Мастер настройки | desk | Setup Wizard |
| Onboarding | Знакомство | desk | Module Onboarding |
| Dock | Док | desk | Dock |
| Recorder | Регистратор запросов | core | Recorder |
| Patch | Патч | core | Patch Log |
| Report | Отчет | общее | Report |
| Settings | Настройки | общее | System Settings |
| System Settings | Системные настройки | core | System Settings |
| Enabled / Disabled | Включено / Отключено | общее | Enabled |
| Active / Inactive | Активен / Неактивен | общее | Active |
| Pending | В ожидании | общее | Pending |
| Completed | Завершено | общее | Completed |
| Failed | Ошибка | статус задания | Failed |
| Approved / Rejected | Утвержден / Отклонен | workflow | Approved |
| Open / Closed | Открыт / Закрыт | общее | Open |
| Posting Date | Дата проводки | общее | Posting Date |
| Due Date | Срок | общее | Due Date |
| Timestamp | Отметка времени | общее | Posting Timestamp |
| Timeline | Хронология | form | Timeline |
| Link (fieldtype) | Ссылка | core / fieldtype | Link |
| Dynamic Link | Динамическая ссылка | core / fieldtype | Dynamic Link |
| Check (fieldtype) | Флажок | core / fieldtype | Check |
| Select (fieldtype) | Выбор | core / fieldtype | Select |
| Table MultiSelect | Таблица множественного выбора | core / fieldtype | Table MultiSelect |
| Attach Image | Прикрепить изображение | core / fieldtype | Attach Image |
| Rating | Оценка | core / fieldtype | Rating |
| Geolocation | Геолокация | core / fieldtype | Geolocation |
| Data (fieldtype) | Данные | core / fieldtype | Data |
| Small Text / Long Text | Короткий текст / Длинный текст | core / fieldtype | Small Text |
| Text Editor | Текстовый редактор | core / fieldtype | Text Editor |
| Float / Int | Число с плавающей точкой / Целое число | core / fieldtype | Float |
| Datetime | Дата и время | core / fieldtype | Datetime |
| Fold | Сгиб | core / fieldtype | Fold |
| Quick Entry | Быстрый ввод | core / DocType | Quick Entry |
| Fetch From | Получать из | core / DocField | Fetch From |
| Perm Level | Уровень доступа | permissions | Perm Level |
| Only If Creator / If Owner | Только для автора / Если владелец | permissions | Only if Creator |
| Select (permission) | Выбор | permissions | Select |
| Read / Write | Чтение / Запись | permissions | Read |
| Mask | Маскировать | permissions | Mask |
| Impersonate | Вход от имени | core / User | Impersonate as {0} |
| Document Status (docstatus) | Статус документа | core | Doc Status |
| Amended Document Naming | Именование исправленных документов | core | Amended Document Naming Settings |
| Amend Counter | Счетчик исправлений | core | Amend Counter |
| Deleted Document | Удаленный документ | core | Deleted Document |
| Submission Queue | Очередь проведения | core | Submission Queue |
| Prepared Report | Подготовленный отчет | core / Report | Prepared Report |
| Snapshot Report | Отчет-снимок | core / Report | Snapshot Report |
| Report Builder | Конструктор отчетов | desk | Report Builder |
| Auto Email Report | Автоотправка отчета по эл. почте | email | Auto Email Report |
| Communication | Сообщение | core | Communication |
| Email Group | Группа рассылки | email | Email Group |
| Email Template | Шаблон письма | email | Email Template |
| Unhandled Email | Необработанное письмо | email | Unhandled Email |
| Reply-To | Адрес для ответа (Reply-To) | email | Reply-To Addresses |
| BCC / CC | Скрытая копия / Копия | email | BCC |
| Read Receipt | Уведомление о прочтении | email | Send Read Receipt |
| Automation Flow | Сценарий автоматизации | automation | Automation Flow |
| Automation Run | Запуск автоматизации | automation | Automation Run |
| Trigger | Триггер | automation | Trigger Type |
| Step Condition | Условие шага | automation | Step Condition |
| Alias (record alias) | Псевдоним | automation | Output Alias |
| Rate Limit | Ограничение частоты | core | Enable Rate Limit |
| Background Worker (RQ Worker) | Фоновый обработчик / Обработчик RQ | core | RQ Worker |
| Recorder | Регистратор запросов | core | Recorder |
| System Console | Системная консоль | desk | System Console |
| System Health Report | Отчет о состоянии системы | desk | System Health Report |
| Dock | Док | desk / navigation | Dock Item |
| Dock / Sidebar layer | Слой (приложения / сайта / пользователя) | desk / navigation | site layer |
| Arrangement | Компоновка | desk / navigation | the site's arrangement |
| Shell | Оболочка | desk / navigation | which shell comes up |
| Desktop Icon | Значок рабочего стола | desk | Desktop Icon |
| Quick List | Быстрый список | desk / Workspace | Quick List |
| Custom Block | Пользовательский блок | desk / Workspace | Custom Block |
| Card Break | Разрыв карточки | desk / Workspace | Card Break |
| Widget | Виджет | desk | Added Widgets |
| Layout | Макет | desk | Manage Layouts |
| Swimlanes | Дорожки | desk / Kanban | Swimlanes |
| Form Tour | Тур по форме | desk | Form Tour |
| Module Onboarding | Знакомство с модулем | desk | Module Onboarding |
| Milestone | Веха | automation | Milestone Tracker |
| Reminder | Напоминание | automation | Reminder |
| Awesome Bar | Строка поиска | desk | Open Awesomebar |
| Global Search | Глобальный поиск | desk | Global Search Settings |
| Session Defaults | Значения сеанса по умолчанию | desk | Session Defaults |
| Print Format Builder / Editor | Конструктор / редактор печатных форм | printing | Print Format Editor |
| Print Style | Стиль печати | printing | Print Style |
| Print Heading | Заголовок печати | printing | Print Heading |
| Raw Printing | Прямая печать | printing | Enable Raw Printing |
| PDF Renderer / Generator | Модуль отрисовки PDF / Генератор PDF | printing | PDF Renderer |
| Snippet | Фрагмент | printing | Print Format Snippet |
| Header / Footer (print) | Верхний / нижний колонтитул | printing | Footer HTML |
| Website Theme | Тема сайта | website | Website Theme |
| Web Page Block | Блок веб-страницы | website | Web Page Block |
| Slideshow | Слайд-шоу | website | Website Slideshow |
| Meta Title / Description / Image | Мета-заголовок / мета-описание / мета-изображение | website | Meta Title |
| Breadcrumbs | Навигационная цепочка | website | Breadcrumbs |
| Route Redirect | Перенаправление маршрута | website | Website Route Redirect |
| Connected App | Подключенное приложение | integrations | Connected App |
| Social Login Key | Ключ входа через соцсети | integrations | Social Login Key |
| Push Notification | Push-уведомление | integrations | Push Notification Settings |
| Relay Server | Сервер-ретранслятор | integrations | Relay Server URL |
| Scope (OAuth) | Область доступа | integrations | OAuth Scope |
| Grant Type | Тип гранта | integrations | Grant Type |
| Redirect URI | URI перенаправления | integrations | Redirect URIs |
| Personal Data Deletion Request | Запрос на удаление персональных данных | website / GDPR | Personal Data Deletion Request |
| Energy Point | Балл активности | social | Energy Point Log |
| Salutation | Обращение | contacts | Salutation |
| Mr / Mrs / Ms / Miss / Dr / Prof | Г-н / Г-жа / Г-жа / Мисс / Д-р / Проф. | contacts / setup | Mr |
| Address Line 1 / 2 | Адрес, строка 1 / 2 | contacts | Address Line 1 |
| Billing / Shipping (address type) | Для выставления счетов / Доставка | contacts | Billing |
| Roles: Accounts Manager / User | Менеджер по бухгалтерии / Пользователь бухгалтерии | roles | Accounts Manager |
| Roles: Sales / Purchase Manager | Менеджер по продажам / закупкам | roles | Sales Manager |
| Roles: Sales / Purchase Master Manager | Главный менеджер по продажам / закупкам | roles | Sales Master Manager |
| Roles: Sales / Purchase User | Пользователь продаж / закупок | roles | Sales User |
| Role: System Manager | Системный менеджер | roles | System Manager |
| Role: Workspace Manager | Менеджер рабочих областей | roles | Workspace Manager |
