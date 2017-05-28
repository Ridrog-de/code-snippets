---
title: 'Socialite Migration'
taxonomy:
    category:
        - docs
---

Migration für Socialite

Password und Email des Eigentlichen User Models müssen nullable() sein

Zu dieser Migration gehört ein Model
```
	protected $fillable = [
        'user_id', 'provider', 'provider_id'
    ];

    public function user()
    {
        return $this->belongsTo('App\User');
    }
```


```
<?php

use Illuminate\Support\Facades\Schema;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Database\Migrations\Migration;

class CreateSocialsTable extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('socials', function (Blueprint $table) {
            $table->increments('id');
            $table->integer('user_id');
            $table->string('provider');
            $table->string('provider_id');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('socials');
    }
}

```