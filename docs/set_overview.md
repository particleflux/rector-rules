# Available configuration sets

## SetList::YII_SWIFT_MAILER_TO_SYMFONY_MAILER

Migrates a Yii2 project from using `yiisoft/yii2-swiftmailer` to
`yiisoft/yii2-symfonymailer`.

Note that you need to update your project dependencies on your own.

Should you use codeception yii module for testing sent mails
(`grabLastSentEmail` etc), you also need to override the mailer message class
for your test config. Otherwise, the codeception yii2 module tries to use the
`yii\swiftmailer\Message`.

```php
'mailer' => [
    'messageClass' => \yii\symfonymailer\Message::class,
]
```
