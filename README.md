# test-coupons
This is a test project for employment in one company.  

### Installation

Add repository to composer.json:

    "repositories": [
      {"type": "composer", "url": "https://repo.packagist.com/alexpittech/"},
      {"packagist.org": false}
    ],

Require repository

    composer require AlexPitTech/test-coupons

### Migrations

    php artisan migrate --path=\vendor\AlexPitTech\test-coupons\migrations\

### Configuration

Copy configuration file to laravel configuration folder. If nessasary, setup calback function as proxy provider and anower parsers.

    'proxyProvider' => function (){return 'proxy here';}

Add command to your Console Kernel 

    protected $commands = [
        ...
        '\ClickTest\Coupons\ParsingCommand'
    ];


### Usage

Run console command for add parsing coupons Job to queue

    php artisan coupons:parsing {parserName}

where parser name is specified in configuration file.

And starting queue, do not forget to setup redis, database or etc driver!

    php artisan queue:work

And enjoy my completed task
