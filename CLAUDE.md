# Auto-otpad Kidi — CLAUDE.md

## Projekat

Statički HTML sajt za Auto-otpad Kidi — prodaja polovnih delova za Fiat, Zastavu i Ladu.

- **Live URL**: https://mrpaki.github.io/kidi/
- **GitHub repo**: https://github.com/mrpaki/kidi (branch: main)
- **Jedan fajl**: `index.html` (sav CSS i JS inline)
- **Slike**: `img/` direktorijum

## Deploy

```bash
git add -A && git commit -m "opis" && git push origin main
```

GitHub Pages se automatski osvježava nakon pusha (30–60 sekundi).

## Struktura index.html

- **CSS varijable** — `--bg`, `--panel`, `--wall`, `--purple` (`#c39bff`), `--purple-glow` (`#7c2bff`)
- **Header** — neon sign "Auto-otpad Kidi" (Pacifico font, pulseP animacija)
- **Hero sekcija** — `img/fica-kidi_final.png` (transparentni PNG, crna pozadina uklonjena)
- **Brendovi sekcija** — tri stripe boxa (FIAT / LADA / ZASTAVA)
- **Usluge** — Otkup automobila + Polovne gume (SVG neon-art ilustracije)
- **Kontakt** — mapa, radno vreme
- **Footer** — WebDesign Rondo link sa hover efektom
- **Mobilna sticky traka** — Poziv / Viber / Mapa dugmad sa scale pulse animacijom

## Stripe box layout

| Stripe | Logo | Natpis | CSS klase |
|--------|------|--------|-----------|
| FIAT (red) | lijevo, kružni neon | desno, centriran | `stripe-row stripe-tekst--center` |
| LADA (blue) | desno, eliptični neon | lijevo | `stripe-row stripe-row--rev` |
| ZASTAVA (white) | gore, eliptični neon | ispod, centrirano | (default) |

## Logoi

- `img/fiat-logo.png` — originalni Fiat logo, `.stripe-logo` klasa (kružni `box-shadow` neon, 120px)
- `img/lada-logo.png` — transparentni PNG (BFS flood-fill + pikseli >245 uklonjeni), `.stripe-logo--shape`
- `img/zastava-logo.png` — isti tretman kao Lada, `.stripe-logo--shape`
- `img/fica-kidi_final.png` — hero slika, crna pozadina uklonjena Pillowom

### Neon efekat logoa

- **Fiat**: `box-shadow` prsten na span containeru (`border-radius: 50%`)
- **Lada/Zastava**: `box-shadow` na eliptičnom containeru (`border-radius: 50%`, `width: 150px`, `height: 85px`), logo `transform: scale(1.23)`

## CSS klase (važne)

| Klasa | Opis |
|-------|------|
| `.sign` | Neon font header (Pacifico, purple glow) |
| `.broken` | "Pokvarena" neon cijev (blinking animacija) |
| `.stripe` | Brand box (FIAT/LADA/ZASTAVA) |
| `.stripe-row` | Flex red layout (logo + tekst horizontalno) |
| `.stripe-row--rev` | Obrnuti red (logo desno) |
| `.stripe-logo` | Kružni neon container (Fiat) |
| `.stripe-logo--shape` | Eliptični neon container (Lada/Zastava) |
| `.stripe-tekst--center` | Centriran tekst u stripe-tekst koloni |
| `.neon-art` | SVG neon ilustracije (gume/automobili) |
| `.traka` | Mobilna sticky bottom bar |

## Mobilna sticky traka

Tri dugmeta — Poziv (crvena), Viber (purple), Mapa (zelena):
- `gap: 6px`, `padding: 0 6px`, `border-radius: 10px`
- Scale pulse animacija: `puls` keyframes, svako dugme pomak 0.6s

## TODO

- [ ] Lada stripe `href="#"` → zamijeniti stvarnim URL-om
- [ ] Zastava stripe `href="#"` → zamijeniti stvarnim URL-om
- [ ] Otkup automobila sekcija `href="#"` → zamijeniti URL-om
- [ ] Polovne gume sekcija `href="#"` → zamijeniti URL-om
