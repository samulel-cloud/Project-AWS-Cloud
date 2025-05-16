# 📌​ VPC Personalizzata con CloudFormation

Questo progetto dimostra la creazione di una Virtual Private Cloud (VPC) personalizzata su AWS utilizzando AWS CloudFormation. L'obbiettivo è simulare un'infrastruttura base con subnet pubblica e privata, configurata per un accesso sicuro e controllato ad internet.

>❗​NOTA❗​Tutte le risorse sono state create in un ambiente sandbox, per cui, dopo aver finito il laboratorio le risorse sono state tutte cancellate.

--

#​🏗️​ Architettura del progetto

La VPC è stata progettata secondo una struttura modulare e scalabile, includendo:

- 1 VPC con DNS abilitato
- 2 Subnet: una pubblica e una privata
- 1 Internet Gateway (IGW) per consentire l'accesso a Internet dalla subnet pubblica
- 1 NAT Gateway (NGW) per permettere l'accesso a Internet alla subnet privata
- 2 Route Table, una per subnet con le relative associazioni
- 2 NACL (Network ACL) per il controllo a livello di subnet
- 2 EC2 instance, una per ciascuna subnet
- Elastic IP (EIP) per il NAT Gateway

---

# ​​🔎​ Dettaglio delle risorse

| Risorsa               | Descrizione |
|-----------------------|-------------|
| **VPC**               | 10.0.0.0/16, DNS support attivo |
| **Public Subnet**     | 10.0.1.0/24, mappa IP pubblico abilitata |
| **Private Subnet**    | 10.0.2.0/24, nessun IP pubblico |
| **Internet Gateway**  | Collegato alla VPC per l'uscita della subnet pubblica |
| **NAT Gateway**       | Nella subnet pubblica, usato dalla subnet privata |
| **Route Tables**      | Regole di routing specifiche per accesso a Internet |
| **NACL**              | Controllo del traffico in ingresso e uscita per ciascuna subnet |
| **EC2 Instances**     | Due istanze `t2.micro`, una per subnet, per testare la connettività |

---

# 🛠️ Come procedere 

1. Caricare il file YAML su AWS CloudFormation.
2. Specificare il nome del "KeyPair EC2" esistente.
3. Avviare lo stack e attendere la creazione completa dell'infrastruttura.
4. Le EC2 vengono create automaticamemte: una nella subnet pubblica, una in quella privata.
5. Alla fine dei test, tutte le risorse sono state eliminate.

---

# ⚠️ Note
- L'ambiente è stato utilizzato a scopo didattico e di test.

- Il provisioning è stato fatto in una sandbox personale, e nessuna risorsa è rimasta attiva dopo i test.

- Il parametro KeyName è obbligatorio per accedere in SSH alle istanze EC2.

- Le AZ sono selezionate automaticamente con !Select e !GetAZs.

---

# ​📃​ Diagramma Architetturale

📌 Vedi file "VPC_diagramm" al'interno della cartella per visualizzare un diagramma deyyagliato dell'infrastruttura creata.

# ​📷​ Screenshots

All'interno della cartella "screenshots", puoi trovare screen dello stack con le varie risorse attivate una volta creato.

---

📂 File inclusi
- vpc_template > file yaml utilizzato per la creazione dello stack.

- README.md > questa documentazione

- screenshots_diagramm > i vari screen delle risorse create e il diagramma descrittivo dell?infrastruttura creata.

---

👨‍💻 Autore
Creato da Samuele Parrotta per esercitazione in ambito AWS Cloud & DevOps.





