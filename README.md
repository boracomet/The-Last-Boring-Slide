# Son Sıkıcı Slayt

"The Last Boring Slide" sunumunun Türkçe sürümü. Tek bir HTML dosyasıdır (WebGL 2, gömülü fontlar ve görseller) ve nginx ile sunulur.

## Dokploy

Compose olarak ekleyin, domain ayarında **Container Port: 80** girin. Sunucuda port açılmaz; trafik Dokploy üzerinden gelir.

## Yerelde çalıştırma

```bash
docker compose -f docker-compose.yml -f compose.local.yml up -d
```

Sunum: http://localhost:8080

Farklı port için:

```bash
PORT=9000 docker compose -f docker-compose.yml -f compose.local.yml up -d
```

Durdurmak için:

```bash
docker compose -f docker-compose.yml -f compose.local.yml down
```

## Kısayollar

| Tuş | İşlev |
| --- | --- |
| → / boşluk / tıklama | İleri |
| ← | Geri |
| F | Tam ekran |
| A | Kendiliğinden oynat |
| M | Sesi aç/kapat |
| N | Konuşmacı notları |
| P | Notlar ikinci pencerede |
| O | Tüm slaytlar |
| . | Siyah ekran |

## Dosyalar

- `site/index.html`: sunum
- `nginx/default.conf`: gzip açık nginx ayarı
- `docker-compose.yml`: `nginx:1.27-alpine` servisi (port açmaz)
- `compose.local.yml`: yerelde 8080 portunu açan ek dosya
