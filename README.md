<div align="center">

![C++](https://img.shields.io/badge/C++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![GitHub repo size](https://img.shields.io/github/repo-size/linux07source/ssh-manager?style=for-the-badge&color=purple)
![GitHub last commit](https://img.shields.io/github/last-commit/linux07source/ssh-manager?style=for-the-badge&color=green)

# 🚀 SSH Manager

An elegant, lightweight, and efficient SSH Connection Manager written in C++ for Linux and macOS. Managed entirely from your terminal via an interactive CLI menu.

[Report Bug](https://github.com/linux07source/ssh-manager/issues) · [Request Feature](https://github.com/linux07source/ssh-manager/issues)

</div>

---

## 📋 Indice
1. [Descrizione del Progetto](#-descrizione-del-progetto)
2. [Funzionalità Principali](#-funzionalità-principali)
3. [Struttura del Codice](#-struttura-del-codice)
4. [Installazione Rapida (.deb)](#-installazione-rapida-deb)
5. [Guida al Packaging del .deb](#-guida-al-packaging-del-deb)
6. [Licenza](#-licenza)
7. [Copia il Repo](#-copia-il-repo)

---

## 📝 Descrizione del Progetto

**SSH Manager** nasce dall'esigenza di velocizzare l'accesso ai server remoti senza dover ricordare a memoria indirizzi IP complessi o nomi utente. Sfruttando la potenza di `std::system` integrata in C++ e l'ambiente nativo Linux, l'applicazione si comporta come un wrapper intuitivo sopra il classico comando `ssh`.

Il punto di forza risiede nella **gestione persistente e sicura**: i dati non vengono salvati all'interno della cartella temporanea del programma, ma risiedono stabilmente nella configurazione locale dell'utente corrente.

---

## ✨ Funzionalità Principali

* **Connessione Manuale:** Avvia sessioni SSH istantanee digitando utente e host al volo.
* **Salvataggio Host (Alias):** Assegna nomi mnemonici ai tuoi server (es. `TuoServer`, `RaspberryPi`).
* **Storage Persistente:** Scrittura e lettura automatica nel file di sistema `~/.config/ssh-manager/host_salvati.txt`.
* **Zero Data Loss:** Aggiornare o disinstallare il pacchetto binario `.deb` non toccherà mai i server che hai salvato nella tua Home.

---

## 📄 Licenza

Distribuito sotto Licenza MIT. Vedi il file `LICENSE` per ulteriori dettagli.

---

## 📄 Copia il Repo

```bash
git clone https://github.com/linux07source/ssh-manager.git
```

---


## 🛠️ Struttura del Codice

Il progetto segue il paradigma di programmazione modulare, dividendo le responsabilità in tre file principali per facilitarne la manutenzione e l'estensione:

| File | Tipo | Descrizione |
| :--- | :--- | :--- |
| `main.cpp` | Sorgente C++ | Gestisce il ciclo d'interfaccia dell'applicazione e lo smistamento del menu `switch-case`. |
| `ssh_manager.cpp` | Sorgente C++ | Contiene la logica di business, il parsing dei file (`fstream`) e le chiamate di sistema. |
| `ssh_manager.h` | Header File | Include le definizioni delle funzioni e sfrutta i *compilation guards* per evitare inclusioni multiple. |

---

## 📦 Installazione Rapida (.deb)

Se utilizzi **Linux Mint**, Ubuntu o una qualsiasi distribuzione Debian-based, puoi scaricare il pacchetto precompilato dalla sezione **Releases** di GitHub e installarlo nativamente.

```bash
# 1. Installa il pacchetto scaricato
sudo dpkg -i ssh-manager-package.deb

# 2. Risolvi eventuali dipendenze (opzionale)
sudo apt -f install

# 3. Per avviarlo
ssh-manager
