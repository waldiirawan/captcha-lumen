# Captcha for Lumen

[Captcha for Laravel 5](https://github.com/mewebstudio/captcha)


## Preview
![Preview](http://i.imgur.com/HYtr744.png)

## Install
```
composer require VueOne/captcha-lumen
```


## How to use
```php
    $app->register(VueOne\CaptchaLumen\CaptchaServiceProvider::class);
    class_alias('VueOne\CaptchaLumen\Facades\Captcha','Captcha');
```


## Set
```php
/**
 * captcha set
 */
config(['captcha'=>
    [
        'useful_time' => 5,
        'captcha_characters' => '2346789abcdefghjmnpqrtuxyzABCDEFGHJMNPQRTUXYZ',
        'sensitive' => false,
        'login'   => [
            'length'    => 4,
            'width'     => 120,
            'height'    => 36,
            'angle'     => 10,
            'lines'     => 2,
            'quality'   => 90,
            'invert'    =>false,
            'bgImage'   =>true,
            'bgColor'   =>'#ffffff',
            'fontColors'=>['#339900','#ff3300','#9966ff','#3333ff'],
        ],
    ]
]);
```
### Generate
```
{Domain}/captchaInfo/{type?}
```
```json
{
  "captchaUrl": "http://{Domain}/captcha/default/782fdc90-3406-f2a9-9573-444ea3dc4d5c",
  "captchaUuid": "782fdc90-3406-f2a9-9573-444ea3dc4d5c"
}
```
#### validate
```php
public function checkCaptcha(Request $request, $type = 'default',$captchaUuid)
{
    $this->validate($request,[
        'captcha'=>'required|captcha:'.$captchaUuid
    ]);
    ...
}
```

## Links
* [Intervention Image](https://github.com/Intervention/image)
* [L5 Captcha on Github](https://github.com/mewebstudio/captcha)
* [L5 Captcha on Packagist](https://packagist.org/packages/mews/captcha)
* [For L4 on Github](https://github.com/mewebstudio/captcha/tree/master-l4)
* [License](http://www.opensource.org/licenses/mit-license.php)
* [Laravel website](http://laravel.com)
* [Laravel Turkiye website](http://www.laravel.gen.tr)
* [MeWebStudio website](http://www.mewebstudio.com)
