 
## CPD App

 install laravel/UI 
 - composer require laravel/ui
 - php artisan ui vue --auth 

 role-based authorization system allows   grant /revoke  abilities on a per-user basis.
    migration [ roles,abilities,role_user,ability-role]
    factory(App\User::class, 10)->create();

- assign ability to a role

    namespace App;
    $user = User::find(1);
    $role = Role::firstOrCreate([
        'name' => 'Admin',
        'label' => 'Admin',
    ]);
    $ability = Ability::firstOrCreate([
        'name' => 'manage-course',
        'label' => 'manage course',
    ]);
    $role->allowTo($ability);

- assign role to user
$user->assignRole($role);
$user->roles;
$user->abilities();