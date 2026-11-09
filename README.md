# site-cicd

[![Deploy static site](https://github.com/levchyrakov/site-cicd/actions/workflows/deploy.yml/badge.svg)](https://github.com/levchyrakov/site-cicd/actions/workflows/deploy.yml)

Учебный статический сайт с автоматическим развёртыванием (CI/CD) на GitHub Pages
через GitHub Actions. Лабораторная работа № 6, курс «Информатика», ГУАП.

**Сайт:** https://levchyrakov.github.io/site-cicd/

## Как это работает

При каждом push в ветку `main` запускается workflow `.github/workflows/deploy.yml`:

1. **lint** — проверка качества кода: HTMLHint проверяет HTML-страницы, Stylelint — файл стилей.
2. **deploy** — запускается, только если проверка прошла: сайт собирается в папку `_site`
   (в подвал подставляются номер коммита и время сборки) и публикуется на GitHub Pages.

Значок вверху показывает состояние последнего запуска workflow.

## Структура

| Файл | Назначение |
|------|------------|
| `index.html`, `pipeline.html`, `about.html` | страницы сайта с общим шаблоном |
| `style.css` | общий файл стилей |
| `.htmlhintrc`, `.stylelintrc.json` | правила линтеров |
| `package.json` | версии линтеров и команды `npm run lint` |
| `.github/workflows/deploy.yml` | workflow проверки и деплоя |

## Локальная проверка

```bash
npm install
npm run lint
```
