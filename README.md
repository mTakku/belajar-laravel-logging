<p align="center" >
  <b>POINT UTAMA</b>
</p>

---

> #### INSTALASI
> - PHP 8.1.0
> - LARAVEL 9.1.10

> #### APA ITU LOGGING?
> - Logging merupakan standar industri untuk memantau informasi yang terjadi di aplikasi.
> - Logging melibatkan pengiriman informasi kejadian ke berkas log, database, atau tempat penyimpanan lainnya.
>
> #### LOGGING CONFIGURATION
> - Konfigurasi logging adalah proses menentukan bagaimana dan di mana pesan logging akan dicatat, termasuk tingkat logging, format, tujuan penyimpanan, rotasi log, dan filter pesan.
>
> #### LOGGING FACADE 
> - Log Facade adalah fitur didalam laravel yang memungkinkan kamu untuk mencatat pesan log dengan mudah ke dalam berbagai saluran log yang telah dikonfigurasi.
>
> Berikut contoh log facade :
> ```
>  Log::debug('An debug message.');
>  Log::info("An informational message");
>  Log::error("An error message");
> ```
>
> #### MULTIPLE LOG CHANNEL
> - Multiple Log Channel adalah kemampuan dalam Laravel yang memungkinkan kamu untuk mencatat pesan log ke beberapa saluran log secara bersamaan, memungkinkan pemantauan dan pemecahan masalah yang lebih        efektif.
>
> Berikut contoh kode log channel,slack :
> ```
> 
>    return [
>    ...
>     'channels' => [
>      'single' => [
>          'driver' => 'single',
>          'level' => 'debug',
>        ],
> 
>      'daily' => [
>       'driver' => 'daily',
>           'path' => storage_path('logs/laravel.log'),
>            'level' => env('LOG_LEVEL', 'debug'),
>            'days' => 14,
>    ],
>
>        'slack' => [
>          'driver' => 'slack',
>          'url' => env('LOG_SLACK_WEBHOOK_URL'),
>          'level' => 'critical',
>       ],
>     ],
>    ];
> ```
>
> #### SINGLE
> - Single, Mengirim data log ke single file.
>
> #### DAILY
> - Daily, mengirim data log ke single file, namun setiap hari akan di rotate filenya.
>
> #### SLACK
> - Slack, mengirim data log ke slack.
---
> #### CONTEXT
> - Context dalam logging adalah informasi tambahan yang disertakan bersama dengan pesan log untuk memberikan konteks atau detail lebih lanjut tentang peristiwa yang terjadi, membantu dalam pemecahan       masalah dan pemantauan kinerja aplikasi.
>
> #### SELECTED CHANNEL
> - Selected Channel dalam logging Laravel adalah saluran log tertentu yang dipilih untuk menerima pesan log dari aplikasi. Ini memungkinkan pengguna untuk mengarahkan pesan log ke saluran yang sesuai dengan kebutuhan aplikasi, seperti file teks, sistem log, atau layanan pihak ketiga seperti Slack.
>
> Berikut kode selected channel :
>
> ```
> $slackLogger = Log::channel("slack");
> $slackLogger->error("Hello Slack");
>
>  Log::info("Hello from Laravel");
>  self::assertTrue(true);
> ```
>
---
> #### CONTEXT
> - Context dalam logging memungkinkan penambahan informasi tambahan, seperti data pengguna, secara otomatis tanpa perlu membuat format pesan manual.
>
> Berikut kode context :
>
> ```
> Log::info("This is an informational info", ["user" => "farel"]);
> ```
---
> #### HANDLER
> - Handler dalam logging adalah bagian dari sistem yang menangkap pesan log dan mengirimkannya ke tujuan yang ditentukan, seperti file, sistem log, email, atau layanan pihak ketiga seperti Slack.
>
> Berikut kode handler :
> ```
> $fileLogger = Log::channel("file");
> $fileLogger->info("Information file handler");
> self::assertTrue(true);
> ```
---
> #### Formatter
> - Formatter dalam logging mengatur format dari pesan log sebelum pesan tersebut disampaikan ke tujuan yang ditentukan, seperti file atau layanan pihak ketiga.
> 
> Berikut kode formatter :
> ```
> 'file' => [
>        'driver' => 'monolog',
>        'level' => env('LOG_LEVEL', 'debug'),
>      'handler' => StreamHandler::class,
>       'formatter' => \Monolog\Formatter\JsonFormatter::class,
>      'with' =>
>           'stream' => storage_path("logs/application.log"),
>         ],
>    ],
> 
<p align="center" >
  <b>PERTANYAAN DAN CATATAN TAMBAHAN</b>
</p>

---

> - 

---

<p align="center" >
  <b>KESIMPULAN</b>
</p>

> - Logging penting dalam pengembangan aplikasi untuk mencatat informasi kejadian.


















