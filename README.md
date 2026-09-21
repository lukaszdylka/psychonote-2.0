# PsychNote AI

System zarządzania sesjami terapeutycznymi z transkrypcją głosu i analizą AI.

## Wymagania

- Klucz Anthropic API (console.anthropic.com) — model Claude Haiku
- Supabase (opcjonalnie) — synchronizacja między urządzeniami
- Google OAuth Client ID (opcjonalnie) — backup na Google Drive

## Deploy na Cloudflare Pages

1. Wrzuć repozytorium na GitHub
2. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git
3. Wybierz repozytorium
4. **Framework preset:** None
5. **Build command:** (puste)
6. **Build output directory:** `/`
7. Save and Deploy

## Konfiguracja po wdrożeniu

Przy pierwszym uruchomieniu wpisz klucz API w formularzu startowym.  
Poświadczenia są zapisywane w localStorage i synchronizowane z Supabase — na kolejnych urządzeniach wystarczy podłączyć Supabase, reszta załaduje się automatycznie.

## Supabase — nowa instalacja

W SQL Editor wykonaj kod z ekranu konfiguracji aplikacji (przycisk "Kopiuj SQL").

## Pliki

| Plik | Opis |
|------|------|
| `index.html` | Cała aplikacja (single-file PWA) |
| `sw.js` | Service Worker (tryb offline) |
| `manifest.json` | PWA manifest |
| `config.json` | Konfiguracja serwera (bez kluczy API) |
| `_redirects` | Cloudflare/Netlify redirects |
| `_headers` | Nagłówki bezpieczeństwa (CSP, HSTS) |
