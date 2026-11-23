# WebStudio — лабораторна робота №4

## Як підключити до свого проєкту
Скопіюйте вміст архіву в папку проєкту **з заміною** файлів (папка `images/` лишається вашою).
Структура: `index.html`, `form.html`, `services.html`, `invitation.html`, `css/`, `scss/`, `js/`, `.vscode/`.

## Відповідність завданням
| № | Що зроблено | Де |
|---|---|---|
| 1 | Медіа-запити 768px / 1158px (+ `prefers-reduced-motion`) | `css/*.css`, `scss/*.scss` |
| 2 | Sign in нерухомий на екранах < 768px (`position: fixed`), Back-to-top піднято вище | `signin-btn.css`, `buttom_up.css` |
| 3 | Sign in → модалка автентифікації (`#modal` + `:target`, з JS — `.is-open`, Esc, клік по фону) | `modal.css`, `main.js` |
| 4 | Адаптивне бургер-меню | `mobile-menu.css`, `main.js` |
| 5 | Плавний перехід нагору (`html { scroll-behavior: smooth }`) | `common.css` |
| 6 | Карусель відгуків (scroll-snap + кнопки + крапки) | `#reviews`, `reviews.scss` |
| 7 | Анімації: fade-up у hero, поява при прокручуванні, hover-ефекти | `animations.scss`, `main.js` |
| 8–10 | Сторінка на Bootstrap 5.3.3 (navbar, cards, accordion, форма) | `services.html` |
| 11–12 | Sass: змінні, міксини, вкладеність, партіали | `scss/` |
| 13* | Валідація тільки HTML+CSS (`required`, `pattern`, `type`, `:invalid`, `:user-invalid`, `:placeholder-shown`, `:has`) | `form.html`, `form.css` |
| 14* | Запрошення + конверт + кнопка друку (`@media print`) | `invitation.html` |
| 15 | Виправлено помилки в CSS/HTML (див. нижче) | — |

## Sass (Live Sass Compiler)
1. VS Code → Extensions → **Live Sass Compiler** (Glenn Marks) → Install.
2. Натисніть **Watch Sass** внизу. Налаштування вже в `.vscode/settings.json` (виводить у `/css`).
3. Редагуйте `scss/*.scss` (не `.css`!). Файли `_variables.scss` і `_mixins.scss` — партіали.

## Що виправлено в існуючому коді
- `vsr(...)` → `var(...)`; `var(-main-bg-color)` → `var(--main-bg-color)`; `--accent-hover-colo`; `-success-color`.
- У `hero.css` правило `.section-title` ховало заголовки "Our Team"/"Our Portfolio"; `.header-nav { padding-right:122px }` ламало шапку.
- Було два елементи з `id="modal"` та два `id="menu-toggle"`; незакритий `div` у модалці; видалено закоментований код.
- Стилі `.modal`/`.backdrop` були у двох файлах і конфліктували → залишено один `modal.css`.
- Посилання `team.html` / `portfolio.html` (їх немає) → якоря `#team`, `#portfolio`.
- Пошук прихований < 1158px, щоб шапка не переповнювалась.

## Обмеження
Збіг "Password" і "Confirm password" без JavaScript перевірити неможливо — це відомий ліміт чистого HTML/CSS.

## Хостинг (пп. 16–19)
1. Перед викладанням: перевірте, що всі шляхи в `images/` існують; видаліть `.vscode/` і `scss/` за бажанням.
2. netlify.com → Sign up → **Add new site → Deploy manually** → перетягніть папку проєкту (там де `index.html`).
3. Скопіюйте посилання `https://....netlify.app`, покажіть викладачу, прикріпіть на сторінці курсу ZIP + посилання.
