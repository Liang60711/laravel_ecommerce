# demo on gcp 
(link)[http://35.221.204.173/]

# 安裝套件
1. livewire `composer require livewire/livewire`
2. 登入註冊功能 Jetstream `composer require laravel/Jetstream`


# Steps
* Layouts
    1. 建立專案 `composer create-project --prefer-dist laravel/laravel <project_name> "8.*"`
    2. 設定資料庫 **.env**
    3. 建立 **resources\views\layouts\\**，設定 css, js 路徑
    4. 建立 livewire `php artisan make:livewire HomeComponent`，在**app\Http\Livewire\HomeComponent\\**設定，設定路由，然後設定模板。
    5. 建立 livewire `php artisan make:livewire ShopComponent`, `php artisan make:livewire CarComponent`, `php artisan make:livewire CheckoutComponent`，呈上。(blade.php 檔案不能用 comment 符號開頭，會有亂碼)

* Authentication
    1. 安裝 Jetstream 套件，並執行 `php artisan jetstream:install livewire`，Livewire 和 Blade 一起使用。
    2. 更改 **database\migrations\2014_10_12_000000_create_users_table.php**，加入 utype 欄位，並 `php artisan migrate`。
    3. 在 **base.blade.php** 寫登入邏輯。
    4. 註冊 admin, user 帳號，並進入資料庫將 admin 的 utype 改成 ADM。
    5. 新增 route 給 admin, user；並執行 `php artisan make:middleware AuthAdmin`。
    6. **app\Http\Middleware\AuthAdmin.php**，新增 utype 條件。
    7. **app\Http\kernel**，在 `protected $routeMiddleware` 中新增 `'authadmin' => \App\Http\Middleware\AuthAdmin::class`
