---
title: Factorys
taxonomy:
    category:
        - docs
---


```
$factory->define(App\Models\Legacy::class, function (Faker\Generator $faker) {

    return [
        'name' => $faker->name,
        'user_id' => function(){
            return factory(App\User::class)->create()->id;
        }
    ];
});
```

```
$users = factory(App\User::class, 100)->create();

foreach ($users as $user){
  factory(App\Models\Legacy::class, 2)->create(['user_id' => $user->id]);
}
```