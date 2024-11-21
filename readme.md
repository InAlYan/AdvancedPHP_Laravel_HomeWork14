# Продвинутое программирование на PHP — Laravel
## Домашняя работа №14

---

Цели практической работы:

— Научиться интегрировать админ-панель в проект. \
— Разобраться в настройке CRUD-методов для сущности в voyager. \

Что нужно сделать:

В этой практической работе вы создадите панель администратора для склада интернет-магазина.

### 1. Создайте новый проект Laravel или откройте уже существующий.

---
![new project](storage\app\public\img\1_0.png "new project")
![new project](storage\app\public\img\1_1.png "new project")
![new project](storage\app\public\img\1_2.png "new project")
![new project](storage\app\public\img\1_3.png "new project")
![new project](storage\app\public\img\1_4.png "new project")
![new project](storage\app\public\img\1_5.png "new project")

---

### 2. Создайте новую ветку вашего репозитория от корневой (main или master).

### 3. Создайте класс Category (модель, миграцию и контроллер) командой php artisan make:model Category -m

### 4. Опишите миграцию для таблицы categories c типами полей:

```
$table->id();
$table->string('name');
$table->timestamps();
```

### 5. Создайте класс Product (модель, миграцию и контроллер) командой php artisan make:model Product -m

### 6. Опишите миграцию для таблицы products c типами полей:

```
$table->string('sku');
$table->id();
$table->string('sku');
$table->string('name');
$table->foreignId('category_id')->constrained();
```

### 7. Выполните миграцию командой php artisan migrate

### 8. Установите voyager командой composer require tcg/voyager

### 9. Выполните установку voyager внутри вашего приложения командой php artisan voyager:install

### 10. Создайте администратора вашего приложения командой php artisan voyager:admin your@email.com

### 11. Войдите в панель администратора, перейдите во вкладку tools/bread и добавьте возможность редактирования сущностей category и product.

### 12. После создания CRUD для сущности product перейдите в эту сущность и нажмите на кнопку Create A Relationship.

### 13. Настройте связь следующим образом:

---
![связь](storage/app/private/img/13_0.png "связь")


---

### 14. Сохраните связь.

### 15. Создайте категорию, а после — тестовый товар, прикреплённый к этой категории.

### 16. Создайте в проекте директорию App/Admin/Widgets и добавьте туда два виджета: ProductsWidget и CategoriesWidget.

### 17. Реализуйте в этих виджетах счётчики количества товаров и категорий.

### 18. Добавьте виджеты в конфигурационный файл voyager.php:

```
'widgets' => [
\App\Admin\Widgets\ProductsWidget::class,
\App\Admin\Widgets\CategoriesWidget::class,
],
```
