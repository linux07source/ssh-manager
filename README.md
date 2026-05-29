<div align="center">

![C++](https://img.shields.io/badge/C++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![macOS](https://img.shields.io/badge/macOS-000000?style=for-the-badge&logo=apple&logoColor=white)
![Snap Store](https://img.shields.io/badge/Snap_Store-black?style=for-the-badge&logo=snapcraft&logoColor=white)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/linux07source/ssh-manager?style=for-the-badge&color=orange)
![GitHub repo size](https://img.shields.io/github/repo-size/linux07source/ssh-manager?style=for-the-badge&color=purple)
![GitHub last commit](https://img.shields.io/github/last-commit/linux07source/ssh-manager?style=for-the-badge&color=green)

# 🚀 SSH Manager

An elegant, lightweight, and efficient SSH Connection Manager written in C++ for Linux and macOS. Managed entirely from your terminal via an interactive CLI menu.

[Scarica l'Ultima Release](https://github.com/linux07source/ssh-manager/releases/tag/ssh-manager-V1.0.0) · [Report Bug](https://github.com/linux07source/ssh-manager/issues) · [Request Feature](https://github.com/linux07source/ssh-manager/issues)

</div>

---

## 📋 Indice
1. [Descrizione del Progetto](#-descrizione-del-progetto)
2. [Funzionalità Principali](#-funzionalità-principali)
3. [Struttura del Codice](#-struttura-del-codice)
4. [Metodi di Installazione](#-metodi-di-installazione)
   * [1. Via Snap (Consigliata)](#-1-via-snap-consigliata)
5. [Compilazione da Sorgente](#-compilazione-da-sorgente)
6. [Licenza](#-licenza)

---

## 📝 Descrizione del Progetto

**SSH Manager** nasce dall'esigenza di velocizzare l'accesso ai server remoti senza dover ricordare a memoria indirizzi IP complessi o nomi utente. Sfruttando la potenza di `std::system` integrata in C++ e l'ambiente nativo del terminale, l'applicazione si comporta come un wrapper intuitivo sopra il classico comando `ssh`.

Il punto di forza risiede nella **gestione persistente e sicura**: i dati non vengono salvati all'interno della cartella temporanea del programma, ma risiedono stabilmente nella configurazione locale dell'utente corrente.

---

## ✨ Funzionalità Principali

* **Connessione Manuale:** Avvia sessioni SSH istantanee digitando utente e host al volo.
* **Salvataggio Host (Alias):** Assegna nomi mnemonici ai tuoi server (es. `TuoServer`, `RaspberryPi`).
* **Storage Persistente:** Scrittura e lettura automatica nel file di sistema `~/.config/ssh-manager/host_salvati.txt`.
* **Zero Data Loss:** Aggiornare o disinstallare l'applicazione (via Snap, APT o `.deb`) non toccherà mai i server che hai salvato nella tua Home.

---

## 🛠️ Struttura del Codice

Il progetto segue il paradigma di programmazione modulare, dividendo le responsabilità in tre file principali per facilitarne la manutenzione e l'estensione:

| File | Tipo | Descrizione |
| :--- | :--- | :--- |
| `main.cpp` | Sorgente C++ | Gestisce il ciclo d'interfaccia dell'applicazione e lo smistamento del menu `switch-case`. |
| `ssh_manager.cpp` | Sorgente C++ | Contiene la logica di business, il parsing dei file (`fstream`) e le chiamate di sistema. |
| `ssh_manager.h` | Header File | Include le definizioni delle funzioni e evita inclusioni multiple. |

---

## 📦 Metodi di Installazione

Scegli il metodo di installazione che preferisci per il tuo sistema Linux.

### 🔹 1. Via Snap (Consigliata)
Disponibile per Ubuntu, Linux Mint, Arch Linux, Fedora e la maggior parte delle distribuzioni. Questo metodo garantisce **aggiornamenti automatici silenti** ogni volta che viene rilasciata una nuova versione.

```bash
# Installa lo snap direttamente dallo store ufficiale
sudo snap install ssh-manager-swag

# Avvia il programma da qualsiasi punto del terminale
ssh-manager
