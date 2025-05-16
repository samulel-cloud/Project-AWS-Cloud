# 🌐 Progetto AWS: Sito Statico con S3 + CloudFront

Questo è il primo di una serie di progetti che farò su AWS. Questi progetti sono realizzati all'interno di ambienti "sandbox" formativi. L'obbiettivo di questi esercizi è di apprendere e dimostrare le risorse che mette a disposizione AWS.

---

## 💻​ Tecnologie utilizzate

- **Amazon S3** – per ospitare il sito web statico
- **Amazon CloudFront** – per distribuire i contenuti in maniera sicura, veloce e scalabile
- **HTML5 & CSS3** – per la creazione della pagina web
- **CloudFront Invalidation** – per aggiornare la cache

---

## 🚀 Step-by-step

### 1. Creazione del bucket S3

- Ho creato un bucket S3 con nome univoco
- Abilitato l’hosting statico
- Caricato i file `index.html` e `style.css`
- Impostato `index.html` come documento di default

### 2. Accesso pubblico

- Creata una bucket policy per permettere accesso pubblico ai file statici
- Testato con successo l’accesso da URL HTTP (es. `http://nome-bucket.s3-website-region.amazonaws.com`)

### 3. Distribuzione tramite CloudFront

- Creata una distribuzione CloudFront associata al bucket S3 statico
- Impostato l’origin come endpoint del sito statico, e non del bucket
- Abilitato HTTPS (CloudFront lo supporta nativamente con certificato)
- Specificato `index.html` come comportamento predefinito

### 4. Test HTTPS

- Verificato che il sito fosse raggiungibile via `https://dxxx.cloudfront.net`
- Accesso sicuro e cifrato confermato con browser

### 5. Aggiornamento contenuti

- Dopo modifiche ai file HTML/CSS, ho utilizzato le CloudFront Invalidations per aggiornare la cache e rendere visibili i nuovi contenuti

---

# ⚠️​ Note sul progetto

> Il progetto è stato creato in un ambiente di sandbox temporaneo.
>Al termine della sessione, tutte le risorse sono state eliminate come richiesto dalle policy del laboratorio.
Per questo motivo, il sito non è più online, ma tutta l'esperienza è documentata attraverso questo README e i documenti allegati ad esso.

---

# 📸Screenshot del lavoro

| Passaggio | screenshot |
| --------- | ---------- |
| Sito statico ospitato su S3 (senza CloudFront) |
| Sito distribuito con CloudFront (HTTPS attivo) |

⚠️ Non è disponibile uno screenshot della configurazione interna di CloudFront perché il progetto è stato svolto in un ambiente sandbox temporaneo, e le risorse sono state eliminate alla fine della sessione.

---

## ✅ Competenze acquisite

- Gestione S3 per hosting web
- Gestione permessi tramite IAM policy
- Configurazione base di CloudFront con HTTPS
- Lavoro in ambiente temporaneo con risorse effimere

---

## 📌 Prossimi sviluppi

- Creazione di una VPC Personalizzata
- Deploy di un’istanza EC2 con script di provisioning

---

## 📚 Risorse utili

- [AWS S3 – Hosting statico](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [AWS CloudFront – Introduzione](https://docs.aws.amazon.com/cloudfront/)
- [Guida: policy pubblica S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html)







	



