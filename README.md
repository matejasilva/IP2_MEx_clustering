# Projekat: Istraživanje podataka 2

## Klasterovanje - MEx skup podataka

Ovaj projekat se bavi klasterovanjem podataka sa senzora koji prate ljude dok rade 7 različitih fizioterapeutskih vežbi. Cilj je da grupišemo pokrete i proverimo da li se naši klasteri poklapaju sa stvarnim vežbama.

### Struktura projekta
*   **MEx.ipynb**: Jupyter sveska koja sadrži sav kod (učitavanje, vizuelizaciju, preprocesiranje, klasterovanje i čuvanje modela).
*   **mex/data/**: Originalni (sirovi) podaci sa senzora.
*   **preprocessed_mex/**: Preprocesirani podaci (očišćeni od šuma i smanjene dimenzionalnosti).
*   **models/**: Direktorijum gde se čuvaju top 3 najbolja modela.
*   **requirements.txt**: Spisak biblioteka potrebnih za rad.

---

### Uputstvo za pokretanje (Lokalno okruženje)

Da biste pokrenuli projekat na svom računaru, pratite ove korake:

#### 1. Kreirajte i pokrenite virtuelno okruženje (venv)
Otvorite terminal u ovom folderu i pokrenite:
```bash
# Kreiranje virtuelnog okruženja
python3 -m venv .venv

# Pokretanje okruženja (Linux / macOS)
source .venv/bin/activate

# Pokretanje okruženja (Windows)
.venv\Scripts\activate
```

#### 2. Instalirajte potrebne biblioteke
Dok je virtuelno okruženje aktivirano, instalirajte sve pakete:
```bash
pip install -r requirements.txt
```

#### 3. Pokrenite Jupyter svesku
Nakon instalacije, pokrenite Jupyter i otvorite `MEx.ipynb`:
```bash
jupyter notebook
```
Zatim možete pokrenuti sve ćelije u svesci kako biste videli rezultate, grafike i sačuvali modele.