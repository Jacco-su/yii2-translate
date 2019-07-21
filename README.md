文本翻译
====
腾讯翻译君翻译，百度翻译

[![Latest Stable Version](https://poser.pugx.org/yiier/yii2-translate/v/stable)](https://packagist.org/packages/yiier/yii2-translate) 
[![Total Downloads](https://poser.pugx.org/yiier/yii2-translate/downloads)](https://packagist.org/packages/yiier/yii2-translate) 
[![Latest Unstable Version](https://poser.pugx.org/yiier/yii2-translate/v/unstable)](https://packagist.org/packages/yiier/yii2-translate) 
[![License](https://poser.pugx.org/yiier/yii2-translate/license)](https://packagist.org/packages/yiier/yii2-translate)


Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist yiier/yii2-translate "*"
```

or add

```
"yiier/yii2-translate": "*"
```

to the require section of your `composer.json` file.


Usage
-----

```php
<?php

$config = [
    // HTTP 请求的超时时间（秒）
    'timeout' => 5.0,
    'from' => 'zh', // 源本语言，可选参数，默认是 zh
    'to' => 'en', // 要翻译成的语言，可选参数，默认是 en

    // 可用的平台配置
    'platforms' => [
       'qqtranslation' => [
            'app_id' => '你的 QQ AI 应用ID',
            'app_key' => '你的 QQ AI 应用密钥',
        ],
       'baidu' => [
            'app_id' => '百度翻译应用 ID',
            'app_key' => '百度翻译应用秘钥',
       ],
    ],
];

$translate = new \yiier\translate\Translate($config, 'qqtranslation');

$translate->translate('今天天气怎么样');

$translate->setFrom('zh')->translate('今天天气怎么样');

$translate->setFrom('zh')->setTo('de')->translate('今天天气怎么样');

$translate->setTo('de')->translate('今天天气怎么样');
```

如果使用 `setFrom` 或者 `setTo`，会忽略配置文件中的配置。