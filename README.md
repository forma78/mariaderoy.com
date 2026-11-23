# mariaderoy.com

Статический сайт Maria DeRoy: один `index.html` + картинки в `img/`. Сборка не нужна.

## Структура

| Файл | Зачем |
|---|---|
| `index.html` | Весь сайт. Разделы Library / Work with me / Teaching / Contact открываются через `#hash` |
| `img/` | Фото и обложки проектов, `og.jpg` — превью для соцсетей (1200×630) |
| `favicon.svg` | Иконка во вкладке браузера |
| `404.html` | Страница «не найдено» |
| `CNAME` | Домен для GitHub Pages: `mariaderoy.com` |
| `robots.txt`, `sitemap.xml` | Для поисковиков |
| `.nojekyll` | Отключает обработку Jekyll на GitHub Pages |

## Публикация на GitHub Pages

1. Репозиторий → **Settings → Pages** → Source: *Deploy from a branch*, ветка `main`, папка `/ (root)`.
2. В поле **Custom domain** должно стоять `mariaderoy.com` (берётся из файла `CNAME`).
3. У регистратора домена прописать DNS:

   | Тип | Имя | Значение |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | `<github-логин>.github.io` |

4. Когда DNS обновится (от нескольких минут до суток), включить **Enforce HTTPS**.

## Что заполнить перед запуском

В конце `index.html`, в блоке `/* subscribe + contact */`:

- `CONTACT_EMAIL` — почта для формы контактов. Пока она пустая, форма пишет «The form opens soon».
- Кнопка **Book your Brand Audit** (`href="mailto:?subject=Brand%20Audit"`) открывает письмо без получателя. Подставьте почту или ссылку на календарь/оплату.
- Ссылки **Read full case** (`href="#"`) пока никуда не ведут. Можно указать статьи на Substack.
- В карточках проектов (массив `P` в скрипте) пустые поля `desc`, `site`, `insta` у Bear Den, BSC и Bioheal.

## Локальный просмотр

```sh
python3 -m http.server 8000
# открыть http://localhost:8000
```
