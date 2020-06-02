<h1>Welcome to Laravel 7 framwork with user login authentication tutorial</h1>

<h2>Laravel 7 framework Crud tutorial</h2>
<h5>Step 1:</h5>
<p>Create table <pre>with php artisan make:migration create_products_table --create=products</pre> </p>
<h5>Step 2:</h5>
<p>After create product table go to edit under "database/migration/yyyy_mm_d_000_create_table_name.php" file using your code editor.</p>
<p>under function up section add your table column field name like product name, product description. EX:<pre>
public function up()
{
    Schema::create('products', function (Blueprint $table) {
        $table->id();
        $table->string('name');
        $table->text('detail');
        $table->timestamps();
    });
}</pre></p>
<p>save and run <pre>php artisan migrate</pre> commend.</p>
<p>now we did new column field on exciting product table.</p>
<h5>Step 3:</h5>
<p>Add Resource Route</p>
<p>open your "routes/web.php" file</p>
<p>Add <pre>Route::resource('products','ProductController');</pre></p>
<h5>Step 4:</h5>
<p>Add Controller and Model</p>
<p>go to your root directory and run <pre>php artisan make:controller ProductController --resource --model=Product</pre> </p>
<p>Go to "app/Http/Controllers/ProductController.php" and add 7 types methods by default</p>
<p>After add your field value as protected to use controller under "app/Product.php" file. EX: <pre>protected $fillable = [
        'name', 'detail'
    ];</pre></p>
<h5>Step 5:</h5>
<p>Add Blade Files</p>
<p>In here we create all our page blade file.</p>
<p>1) layout.blade.php</p>

<p>2) index.blade.php</p>

<p>3) create.blade.php</p>

<p>4) edit.blade.php</p>

<p>5) show.blade.php</p>
<p>You can find here under "resource/views/products/" folder to see all code.</p>
<p>Once finish blade file run or see products page url and do crud operation</p>
<p>Laravel 7 basic crud operation done</p>
<h5>Step 6:</h5>
<p>Add your page with user authentication.</p>
<p>Go to "routes/web.php" file and add <pre>Route::get('/', 'ProductController@index')->name('products')->middleware('auth');
Route::resource('products','ProductController')->middleware('auth');</pre></p>
<p>So now without user can't access your dashboard or product crud page.</p>
