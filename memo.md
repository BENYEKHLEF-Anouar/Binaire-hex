Fiche Mémo Personnelle : Conversions Décimal ↔ Binaire ↔ Hex

# 1. Décimal → Binaire

Méthode : décomposer le nombre en puissances de 2 (128, 64, 32, 16, 8, 4, 2, 1).

Exemple : 173₁₀
173 − 128 = 45 → 1
45 − 32 = 13 → 1
13 − 8 = 5 → 1
5 − 4 = 1 → 1
1 − 1 = 0 → 1
→ Binaire : 10101101₂

------------

# 2. Binaire → Décimal

Méthode : somme pondérée des bits (chaque bit vaut 2^n).

Exemple : 10101101₂
1·128 + 0·64 + 1·32 + 0·16 + 1·8 + 1·4 + 0·2 + 1·1 = 173₁₀

------------

# 3. Binaire ↔ Hex

Méthode : grouper les bits par 4 (nibbles) et convertir chaque groupe.

Exemple : 10101101₂
Grouper : 1010 1101 → 0xAD

Exemple : 0x5A → 0101 1010₂

------------

# 4. Décimal → Hex

Méthode : divisions successives par 16, lire les restes.

Exemple : 250₁₀
250 ÷ 16 = 15 r10 → 15 = F, 10 = A → 0xFA

------------

# 5. Hex → Décimal

Méthode : somme pondérée en base 16.

Exemple : 0xFA = 15·16 + 10 = 250₁₀

------------

# 6. Astuces & Pièges

* Toujours préciser la base (0b, 0x ou indice).
* Compléter les groupes de 4 bits à gauche si nécessaire.
* Vérifier un résultat via une méthode alternative (ex : passer par hex).
