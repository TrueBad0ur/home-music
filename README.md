# Setup an s3 bucket on yandex cloud to sync


[official manual](https://yandex.cloud/ru/docs/storage/tools/s3cmd#before-you-begin)
```bash
user@music:~/navidrome/music$ s3cmd --configure
Access Key — введите идентификатор ключа
Secret Key — содержимое статического ключа
Default Region — ru-central1
S3 Endpoint — storage.yandexcloud.net
DNS-style bucket+hostname:port template for accessing a bucket — %(bucket)s.storage.yandexcloud.net
```

If you need to upload:
```bash
user@music:~/navidrome/music$ s3cmd ls
2025-10-21 19:49  s3://music-bucket
...

user@music:~/navidrome/music$ s3cmd put --storage-class ICE --recursive . s3://music-bucket
```

If you need to sync:
```bash
user@music:~/navidrome/music$ s3cmd sync --storage-class ICE . s3://music-bucket
```
