# Rozpis operativy KNL

Webová aplikace pro celoroční plánování operativy Krajské nemocnice Liberec. Pracoviště: Liberec, Turnov a Frýdlant.

Celá aplikace je jeden soubor `index.html`. Nemá žádný build ani server. Data se ukládají v prohlížeči (localStorage). Zálohu a obnovu dat najdete v části **Systém**.

## Hlavní moduly

- **Rozpis sálů:** roční plán sálů po půldnech, LA/CA, sudé a liché týdny, dospávací pokoje a externí sály.
- **Kalendář a časová osa:** velký kalendář provozu, státní svátky a školní prázdniny podle kraje a okresu.
- **Omezení a asanace:** omezení sálů, návrh asanačních dnů, přesun bloků do náhradních sálů a tisk za vybrané období.
- **Personál:** potřeba lékařů, anesteziologických a sálových sester, upozornění na nedostatek a přehled možného volna.
- **Požadavky a kapacity:** požadavky oborů, volné kapacity, kvóty, čekací listiny a zveřejnění plánu.
- **Operační sály 3D:** model nemocnice s živým stavem sálů a editorem plánu budovy.
  - Stavy sálů: volný, příprava, výkon, úklid a Emergency.
  - Trasy transportu včetně výtahů.
  - Režimy Emergency a Hygiena.
- **Role:** koordinátor, obor a management. Aplikace má světlý i tmavý vzhled a tisk každé sekce.

## Spuštění

Otevřete `index.html` v prohlížeči. Případně ho servírujte libovolným statickým serverem:

```bash
npx serve .
```

## Nasazení

Aplikace je statický soubor, takže ji nasadíte kamkoli:

- **GitHub Pages:** v Settings → Pages zvolte větev `main` a složku `/ (root)`.
- **Vercel nebo Netlify:** importujte repozitář, bez build příkazu, výstupní složka `/`.

## Externí závislosti (CDN)

- Font Geist z Google Fonts.
- three.js r128 (cdnjs) a postprocessing z three@0.128.0 (jsDelivr). Načítají se jen v modulu 3D.

Bez internetu funguje vše kromě 3D modelu. Bez postprocessingu se 3D zobrazí bez efektu záře.

## Poznámky

- Stav sálů ve 3D se odvozuje z plánu operativy a pracovní doby. Nejde o napojení na nemocniční systém.
- Rozvržení budovy ve 3D je ukázkové. Upravíte ho v **Editoru plánu**.
