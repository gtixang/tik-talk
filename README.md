<div align="center" style="margin-bottom:20px">
  <img src="apps/tik-talk/public/assets/svg/logo-small.svg" width="110" alt="TikTalk логотип" />
</div>

[![Angular](https://img.shields.io/badge/Angular-20.x-DD0031?logo=angular&logoColor=white)](https://angular.io/)
[![Nx](https://img.shields.io/badge/Nx-21.x-000000?logo=nrwl&logoColor=white)](https://nx.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-%7E5.8-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Jest](https://img.shields.io/badge/Jest-%5E30.0.2-C21325?logo=jest&logoColor=white)](https://jestjs.io/)
[![ESLint](https://img.shields.io/badge/ESLint-9.x-4B32C3?logo=eslint&logoColor=white)](https://eslint.org/)
[![Prettier](https://img.shields.io/badge/Prettier-2.x-F7B93E?logo=prettier&logoColor=white)](https://prettier.io/)

## TikTalk —  веб‑приложение для профилей и ленты.

🚀 **Демо:** [Открыть приложение](https://tik-talk-sepia.vercel.app/)

**Данные для входа:**
- Логин: `runar_n`
- Пароль: `rYr1wTQycE`

## Обзор проекта
- Монорепозиторий содержит одно приложение и набор библиотек в папке libs, которые предоставляют компоненты интерфейса и клиентскую логику.

## Реализованные функции

- Каркас приложения и маршрутизация: основной layout и маршруты для профиля, настроек и поиска.
- Клиент аутентификации: вход, обновление токена и выход; токены сохраняются в cookie (ngx-cookie-service).
- Клиент профилей: получение собственной страницы, получение аккаунта по id, список подписчиков, частичное обновление профиля, загрузка аватара.
- Общие UI‑библиотеки: sidebar, svg‑иконки, заголовок профиля, компоненты постов (post-feed, post-input) — используются на странице профиля.
- Страница логина реализована в компоненте login-page-component.



## Технологии

- Angular ~20.1
- Nx 21.x
- TypeScript ~5.8
- RxJS, zone.js
- Jest (юнит‑тесты)
- Cypress (E2E, присутствует конфигурация в проекте)
- ESLint, Prettier
- ngx-cookie-service

(Точные версии в `package.json`.)


## Архитектура репозитория

- `apps/tik-talk` — основное приложение
- `libs/` — библиотеки с функциональными и общими модулями

Ключевые конфигурационные файлы: `package.json`, `nx.json`.
Статические ресурсы приложения находятся в каталоге `public` внутри приложения.


## Как запустить локально

1. Установить зависимости:

   ```sh
   npm install
   ```

2. Запустить dev‑сервер (открывает браузер):

   ```sh
   npm start
   ```

   Команда выполняет: `npx nx serve tik-talk -o`.

3. Собрать production‑бандл:

   ```sh
   npm run build
   ```

4. Линт и форматирование:

   ```sh
   npm run lint
   npm run format
   ```


## Тестирование

- Unit: Jest

  ```sh
  npx nx test tik-talk
  ```

- E2E: в репозитории присутствует конфигурация Cypress (`apps/tik-talk-e2e`), для запуска используйте соответствующие цели в Nx/скрипты.


## Важные замечания при запуске

- Клиент обращается к внешнему API (в коде указан базовый URL: `https://icherniakov.ru/yt-course/`). Без доступа к этому API функционал профиля и аутентификации будет выдавать сетевые ошибки.
- Токены аутентификации хранятся в cookie под ключами `token` и `refreshToken`.


## Статус проекта

- Состояние: демонстрационный — проект завершён как демо/портфолио, разработка приостановлена.
- Не готов для продакшена без дополнительной конфигурации окружения и аудита безопасности.
