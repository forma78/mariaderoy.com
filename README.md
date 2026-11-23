# mariaderoy.com

Статический сайт Maria DeRoy: один `index.html` и картинки в `img/`. Сборка не нужна.

## Главное правило

**Источник правды — эта папка на локальном диске.**

- Все правки делаются здесь. Отсюда они пушатся в GitHub `forma78/mariaderoy.com` (ветка `main`), а оттуда Vercel публикует сайт.
- Файлы с GitHub сюда не скачивать и в обратную сторону ничего не тянуть. GitHub нужен только как канал для деплоя.
- Старую копию легко узнать: она называлась `mariaderoy` (без `.com`). Её копии на GitHub и Vercel удалены 23.11.2026. Если где-то всплывёт `mariaderoy` без `.com`, не использовать.

## Как обновить сайт

```sh
cd ~/mariaderoy.com
git add -A
git commit -m "что поменяли"
git push
```

После пуша Vercel сам публикует новую версию, обычно за минуту.

## Что в папке

| Файл | Что это |
|---|---|
| `index.html` | Весь сайт: стили, разметка, скрипт, SEO-теги. Разделы Library / Work with me / Teaching / Contact / Thank you открываются через `#hash` |
| `img/` | Фото и обложки проектов, `og.jpg` — превью для соцсетей (1200×630) |
| `favicon.svg` | Иконка во вкладке браузера |
| `404.html` | Страница «не найдено» |
| `robots.txt`, `sitemap.xml` | Для поисковиков |
| `.vercelignore` | Не даёт опубликовать этот README на сайте |
| `CNAME`, `.nojekyll` | Остались от GitHub Pages. Vercel их не использует, но и не мешают |

## Настройки (переменные в скрипте внизу `index.html`)

- `CONTACT_EMAIL`: почта для страницы Contact. Пока пусто, адрес не показывается, а форма пишет «The form opens soon».
- `SUBSCRIBE_URL`: Substack.
- `STRIPE_LINK`: ссылка Stripe Payment Link (`https://buy.stripe.com/...`) для кнопки «Book your Brand Audit». Та же ссылка стоит в `href` самой кнопки (`id="payBtn"`); при замене ссылки менять в обоих местах.
- `BOOKING_URL`: ссылка Calendly, которая показывается на странице «Thank you» после оплаты.

## Оплата (Stripe)

- Brand Audit продаётся через Stripe Payment Link.
- В настройках ссылки, в разделе «After payment», должна стоять переадресация на `https://mariaderoy.com/?paid=1`. С этого адреса открывается страница «Thank you» (`#thanks`) с кнопкой Calendly.

## Что ещё не заполнено

- Ссылки **Read full case** (`href="#"`) пока никуда не ведут. Можно поставить статьи на Substack.
- В карточках проектов (массив `P` в скрипте) пустые поля `desc`, `site`, `insta` у Bear Den, BSC и Bioheal.

## Локальный просмотр

```sh
python3 -m http.server 8000
# открыть http://localhost:8000
```
