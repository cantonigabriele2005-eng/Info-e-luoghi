# Scheda dati: Evento e Sede

## Entità

Il dataset contiene due entità: **Evento** e **Sede**. Attualmente i dati comprendono **6 eventi** e **3 sedi**.

---

## Entità Sede

Chiave primaria: `id` (numerico, intero, univoco in `Sede`, stabile nel tempo).

| Campo | Tipo | Esempio | Note |
|---|---|---|---|
| `id` | numero intero | `1` | Chiave primaria |
| `nome` | testo | `Teatro Comunale` | [da completare] |
| `indirizzo` | testo | `Via Roma 1, Milano` | [da completare] |
| `capienza` | numero intero | `300` | [da completare] |

---

## Entità Evento

Chiave primaria: `id` (numerico, intero, univoco in `Evento`, stabile nel tempo).

| Campo | Tipo | Esempio | Note |
|---|---|---|---|
| `id` | numero intero | `101` | Chiave primaria |
| `titolo` | testo | `Concerto di primavera` | [da completare] |
| `data` | data (AAAA-MM-GG) | `2026-04-12` | [da completare] |
| `sede_id` | numero intero | `1` | Chiave esterna: riferisce a `Sede.id` |

---

## Relazione

- Una **Sede** può ospitare **più Eventi** (uno-a-molti).
- Ogni **Evento** si svolge in **una sola Sede**.
- `Evento.sede_id` fa riferimento a `Sede.id`.

---

## Schema Evento–Sede

```mermaid
erDiagram
    SEDE ||--o{ EVENTO : ospita
    SEDE {
        int id PK
        string nome
        string indirizzo
        int capienza
    }
    EVENTO {
        int id PK
        string titolo
        date data
        int sede\_id FK
    }
