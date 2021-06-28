# 安裝套件
1. livewire `composer require livewire/livewire`
2. 


# Steps
1. 建立專案 `composer create-project --prefer-dist laravel/laravel <project_name> "8.*"`
2. 設定資料庫 **.env**
3. 建立 **resources\views\layouts\\**，設定 css, js 路徑
4. 建立 livewire `php artisan make:livewire HomeComponent`，在**app\Http\Livewire\HomeComponent\\**設定，並設定路由。