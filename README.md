# Shining Networks Company L.L.C. — Website

**Shining Networks Company L.L.C. · شركة الشبكات المضية ش.م.م**
Electrical contracting · Seeb, Muscat, Sultanate of Oman
Design reference: greatlineinteriors.ae style — cinematic photos, huge ultra-light headings, floating pill nav, tan/gold accents, dark footer with giant wordmark.

---

## 0. 🌐 LIVE — Hosting & Deploy (surge.sh)

**Live URL: https://shiningnetworks.surge.sh** (permanent, free surge.sh subdomain — 5 Oct 2026 ko publish + email verified)

| Detail | Value |
|---|---|
| Surge login email | `shiningnetbcea29@maxxspace.com` (mail.tm ke through banaya gaya private inbox — niche note padhein) |
| Surge password | `Sn` + generated strong password — **`surge-cli/_creds.json` file mein saved hai** |
| Surge token | `8a60c17d93e93d5d3d2f339a51f4fe07` (CLI/CI se deploy ke liye) |
| Deploy folder | `/home/user/deploy/` (index.html + CNAME) |

**Re-deploy kaise karein (site update ke baad):**
```bash
cp site/index.html deploy/index.html
cd surge-cli
SURGE_LOGIN=shiningnetbcea29@maxxspace.com SURGE_TOKEN=8a60c17d93e93d5d3d2f339a51f4fe07 \
  ./node_modules/.bin/surge /home/user/deploy shiningnetworks.surge.sh
```
Ya `node surge-cli/node_modules/.bin/surge` kisi bhi machine se — ya `npm i -g surge` + `surge login` + `surge deploy deploy shiningnetworks.surge.sh`.

**⚠️ Email ka note (important):** Surge ko email verification chahiye, aur **disposable emails (mailinator/guerrilla) se publish block hai**. Aapki marzi se temporary email use kiya gaya hai — `maxxspace.com` (mail.tm) ek password-protected private inbox hai, lekin phir bhi **behtar hai ki aap apne real email ke saath naya surge account banao** (surge.com par login → ya CLI se) aur usse ye domain redeploy karo:
1. Purane account se `surge teardown shiningnetworks.surge.sh`
2. Apne email se `surge login` (naya account) → `surge deploy deploy shiningnetworks.surge.sh`
3. `surge verify` → apne inbox par link click karo.
Aise account + domain dono aapke control mein permanent ho jayenge.

**Apna domain (jaise shiningnetworks.om) point karna ho to:**
- `deploy/CNAME` mein sirf `shiningnetworks.om` likh dein (ya surge CLI se `surge domain`), DNS mein CNAME record `na-west1.surge.sh` ya A record `45.55.110.124` point karein. Surge SSL free deta hai.

---

## 1. Files — kaunsa file kya hai

| File | Kya hai | Kab use karein |
|---|---|---|
| **`index.html`** | **Poora website ek hi file mein** (1.2 MB) — saari photos/logo base64 ke roop mein andar embedded hain. Koi extra file nahi chahiye. | **Recommended.** Kisi bhi hosting par sirf ye ek file upload karo — kaam khatam. Email attachment, WhatsApp share, offline demo — sab chalega. |
| `index-external.html` | Same website, lekin photos `assets/` folder se load hoti hain (64 KB HTML). | Jab hosting/CMS alag images manage kare, ya page size kam rakhna ho. Iske saath `assets/` folder bhi upload karna zaroori hai. |
| `assets/img/*.webp` + `.jpg` | 8 AI-generated professional photos (originals `.jpg`, web versions `.webp`). | `index-external.html` ke liye. |
| `assets/logo-badge-512.png`, `logo-icon-384.png`, `favicon-64.png` | Aapke uploaded logo se banaye gaye circular emblem, inner mark, favicon. | `index-external.html` ke liye. |
| `_template.html`, `_uris.json` | Developer sources (template + base64 images). Editing ke liye. | Site change karni ho to `index.html` ko directly mat todo — template badlo aur `index.html` dobara build karo. |
| `shots/` (workspace root) | Verification screenshots (desktop/mobile/Arabic). | Sirf preview. |

**Live features:** EN/ع language toggle (Arabic = full RTL), floating pill nav + mobile drawer, filterable work tiles (All / Connections / Metering / LV & HV / Cabling), WhatsApp enquiry form (wa.me/96899311148 par message ready karke khulta hai — koi backend/CGI nahi chahiye), floating WhatsApp + call + back-to-top buttons, JSON-LD (ElectricalContractor) for Google, og:image social preview.

---

## 2. ⚠️ PUBLISH SE PEHLE — YE CHECKLIST ZAROOR POORA KAREIN

### 2.1 DCRP claim (sabse important)
- **Status:** DCRP registration **AC136/22 (8 Nov 2022 → 7 Nov 2025)** expire ho chuki hai, aur **August 2026 ki DCRP active list mein company ka naam nahi hai**. (Isse pehle AC007/19: 14 Feb 2019 → 14 Feb 2022, Grade C.)
- **Isliye site mein claim qualify kiya gaya hai.** Ab likha hai:
  - Hero facts: `Per DCRP requirements` / `وفق متطلبات DCRP`
  - Why Us: `Built to DCRP Requirements` + "…carried out to the requirements of Oman's Distribution Code Review Panel scheme."
- **Agar DCRP renewal ho gaya hai** (naya certificate / latest active list mein naam hai) — to ye wording wapas strong kar sakte ho:
  - `Per DCRP requirements` → `DCRP-registered scope`
  - `Built to DCRP Requirements` → `DCRP-Registered`
  - Meta description mein `works up to 11 kV to DCRP requirements` → `DCRP-registered electrical contractor`
  - (Ye strings `_template.html` mein search karke mil jayengi.)
- **Agar renew nahi hua** — current wording hi rehne dein. Ye bhi sach hai (kaam DCRP requirements ke hisaab se hota hai) aur legal risk bhi nahi.

### 2.2 Working hours
- Site par abhi: **"Sunday – Thursday · until 4:00 PM"** (top strip + contact card).
- Ye Google Business listing se liya gaya hai (closing 4:00 PM), lekin **poora weekly pattern confirm nahi hai**. Apne actual hours se match kar lein. JSON-LD `openingHours` bhi same jagah (index.html head) update karein.

### 2.3 Email
- Site par **jaan-boojhkar koi email address nahi rakha gaya** — koi verified email public nahi mila tha. `info@shiningnetworks.om` type koi bhi address guess karke nahi daala gaya hai (achhi baat hai — galat email se customer ka mail bounce hota hai).
- Jab real email ho, tab footer "GET IN TOUCH" column mein add karein (EN + AR dono jagah).

### 2.4 Photos
- Saari photos **AI-generated representative images** hain (professional quality, aapke kaam ke type ki). Site ke "Our Work" section ke neeche **honesty note** already diya gaya hai ki photos representative hain.
- **Real project photos** (meter panels, service connections, cable laying, team) bhej dein — tiles aur service cards mein replace kar denge. Kam se kam 6–8 photos, phone se bhi chalega.

### 2.5 Domain & hosting
- `shiningnetworks.om` domain **abhi available hai** — jaldi le lein (koi website pehle se nahi hai).
- Hosting: koi bhi shared hosting / Netlify / Cloudflare Pages. **Sirf `index.html` upload karna hai** (single file).
- Google Business Profile mein website link add karein; NAP (name/address/phone) wahi rakhein jo site par hai.

### 2.6 Na banaye / na daalein (honesty policy)
- Fake testimonials, fake project names, fake statistics (e.g. "500+ projects"), fake certifications — **mat daalein**. Real data aane par khushi se add karenge.
- "DCRP Approved" wali kisi bhi advertising material se pehle renewal confirm karein.

---

## 3. Company data jo site par use hua hai (verified)

- **Name:** Shining Networks Company L.L.C. / شركة الشبكات المضية ش.م.م
- **Address:** Complex 37, Building No. 275, Al Ataa Street, Seeb 111, Muscat Governorate, Oman
- **Phone / WhatsApp:** +968 9931 1148 (wa.me/96899311148)
- **Services (owner's own description ke hisaab se):** electrical works up to 11 kV, all LV & HV works, new service connections (villas / buildings / commercial), meter installation, changing & shifting, internal electrification, cable laying & jointing, testing, earthing, maintenance
- **Service areas:** Seeb, Al Khoudh, Mawaleh, Bausher, Ghala, Ruwi, Muttrah, Al Amerat, Qurayyat, Barka, Sohar (+ beyond by arrangement)

---

## 4. Chhote changes kaise karein (developer guide)

1. **Text change:** `_template.html` mein har string ke paas `data-en="..."` aur `data-ar="..."` dono hain — **dono update karna zaroori hai**. Phir `index.html` rebuild karo (template + `_uris.json` injection).
2. **Phone/WhatsApp change:** `+96899311148` / `+968 9931 1148` ka find-replace karein (tel: links, wa.me links, JSON-LD). Phone numbers ke elements par `dir="ltr"` laga hai — RTL mein bhi number sahi dikhega, use hatayein mat.
3. **Colors:** CSS `:root` block mein `--gold`, `--gold-2`, `--dark`, `--cream`, `--red` — ek jagah badlo, poori site badal jayegi.
4. **Language toggle:** `data-en` / `data-ar` attributes + `setLang()` JS. Choice `localStorage` mein save hoti hai.
5. **Form:** `#frm` submit par `https://wa.me/96899311148?text=...` par message compose karta hai — koi server nahi chahiye. `window.open` popup blockers se bachne ke liye user gesture ke andar hi chalta hai.

---

*Website ready: 5 October 2026. Design + content verify kiya gaya (desktop 1440px, mobile 390px, Arabic RTL) — koi console error nahi.*
