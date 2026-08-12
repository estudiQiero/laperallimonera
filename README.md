# La Pera Llimonera — clon Astro

Port fidel de la web WordPress (`laperallimonera.cat`) a Astro, reconstruït a
partir del tema real (`temaLaPera`): `header.php`, `footer.php`,
`plantilles/index-codiHome.php` i tot el `main.scss` original (mateixos
colors, tipografies Quicksand/Roboto Slab, i totes les classes CSS).

## Posar en marxa

```bash
npm install
npm run dev       # http://localhost:4321
npm run build     # genera /dist (web estàtica llesta per pujar a qualsevol hosting)
npm run preview   # previsualitza el build de producció
```

## Què és fidel al 100%

- Estructura HTML de totes les seccions (hero, qui som, manteniment,
  seguretat, SEO, "T'ho fem fàcil", testimonis, formulari, footer).
- Tots els textos en català, textuals.
- Colors, tipografies i el `main.scss` sencer del tema original (`src/styles/legacy/`).
- Menú hamburguesa amb el mateix comportament JS.
- Totes les imatges/il·lustracions reals (Metge, Lladregot, Polisman,
  Shakespeare, logos WordPress/Woo/Prestashop/Shopify, fotos, etc.)

## Coses pendents / substituïdes (assets que no hi eren a la carpeta connectada)

1. **Logo principal `Logo-LaPera-Consultors.svg`** — no s'ha trobat el SVG
   original; s'utilitza `logo-LaPera-800W.webp` com a substitut
   (`public/wp-content/uploads/2024/10/Logo-LaPera-Consultors.webp`).
2. **Icona de política de privadesa** (`Icona-PoliticaPrivacitat.svg`, footer)
   — no trobada; s'ha creat una icona simple de substitució.
3. **Logo d'Amorino** (`logo-amorino-600W.webp`, testimonis) — no trobat en
   format web (només hi ha un `.svg` de 6,5MB sense optimitzar); de moment es
   mostra el nom "Amorino" en text. Substituïu-lo per la imatge real quan la
   tingueu optimitzada.
4. **Sprites d'icones** `tira-icones-salut.svg` (4 icones, secció
   Manteniment) i `tira-icones-seguretat.svg` (9 icones, secció Seguretat) —
   no trobats. S'han creat icones de línia pròpies a
   `public/wp-content/uploads/2024/10/icones/` amb els colors de marca
   (ocre sobre fons verd fosc, marró sobre fons ocre). Substituïu-les pels
   fitxers originals si en teniu.
5. **Formulari de contacte**: reproduït visualment igual (mateixos camps:
   Nom, Empresa/Botiga, Mail, Telèfon, Missatge, checkbox de privadesa) però
   sense backend — l'Astro és estàtic. Cal connectar-lo a un servei
   (Formspree, Netlify Forms, un endpoint propi, etc.) abans de publicar.
6. **Joc "7 i mig"**: NO inclòs en aquesta entrega (es farà més endavant,
   segons demanda). L'enllaç del menú apunta a `/7iMig/index.html`, on
   caldrà col·locar el joc quan estigui fet.
7. **Chat Tawk.to** del footer original: no inclòs (feu-me-ho saber si el
   voleu reincorporar).

## Estructura

```
src/
  layouts/Layout.astro      — <head>, fonts, meta
  components/Header.astro   — port de header.php
  components/Footer.astro   — port de footer.php
  pages/index.astro         — port de plantilles/index-codiHome.php
  styles/
    site.scss               — entrada principal
    legacy/                 — SCSS original del tema (gairebé sense tocar)
public/
  wp-content/uploads/2024/10/  — imatges amb el mateix path que l'original
  favicon/
```
