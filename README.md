# Projekat: Istraživanje podataka 2

## Klasterovanje - MEx skup podataka

Ovaj projekat se bavi klasterovanjem podataka sa senzora koji prate ljude dok rade 7 različitih fizioterapeutskih vežbi. Cilj je da grupišemo pokrete i proverimo da li se naši klasteri poklapaju sa stvarnim vežbama.

### O datasetu

MEx (Multi-modal Exercise) je dataset koji sadrži snimke 30 ispitanika dok rade fizioterapeutske vežbe. Koriste se 4 senzora:
- **act** - akcelerometar na butini
- **acw** - akcelerometar na ručnom zglobu
- **pm** - prostirka pritiska (pressure mat)
- **dc** - dubinska kamera (depth camera)

Svaki ispitanik radi 7 vežbi, pa ukupno imamo 239 sesija (vežba 4 se radi na obe strane tela).

### Šta je urađeno

1. **Učitavanje i vizuelizacija** - učitani su sirovi podaci sa svih senzora i prikazani grafici da se vidi kako izgledaju signali
2. **Preprocesiranje** - popunjene nedostajuće vrednosti, PCA redukcija za kameru i prostirku (na 15 komponenti), Z-score standardizacija
3. **Ekstrakcija obeležja** - iz svake sesije su izvučena statistička obeležja (mean, std, min, max, a za akcelerometre i RMS i raspon)
4. **Klasterovanje** - testirano je 5 algoritama (K-Means, Agglomerative, Spectral, GMM, Birch) sa n_clusters=7
5. **Pretraga kombinacija senzora** - isprobane su sve kombinacije od 2, 3 i 4 senzora da se vidi koja daje najbolji rezultat
6. **Čuvanje modela** - top 3 modela su sačuvana u `models/` folder

Glavni kriterijum za poređenje je **ARI (Adjusted Rand Index)** koji pokazuje koliko se klasteri poklapaju sa pravim oznakama vežbi.

### Struktura projekta
*   **MEx.ipynb** - Jupyter sveska sa celokupnim kodom
*   **mex/data/** - sirovi podaci sa senzora
*   **preprocessed_mex/** - preprocesirani podaci
*   **models/** - top 3 sačuvana modela
*   **requirements.txt** - potrebne biblioteke

---

### Pokretanje

#### 1. Virtuelno okruženje
```bash
python3 -m venv .venv

# Linux / macOS
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

#### 2. Instalacija paketa
```bash
pip install -r requirements.txt
```

#### 3. Pokretanje
```bash
jupyter notebook
```
Otvorite `MEx.ipynb` i pokrenite sve ćelije redom.