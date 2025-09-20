Fiche de Révision & Exercices sur les Opérations Bit à Bit

Opérateurs sur les Bits

* AND (&) : les deux doivent être activés → conserve seulement les 1 présents dans les deux.
  Exemple : 1100 & 1010 = 1000
* OR (|) : au moins un activé → combine les 1.
  Exemple : 1100 | 1010 = 1110
* XOR (^) : différent gagne → activé seulement si les bits sont différents.
  Exemple : 1100 ^ 1010 = 0110
* NOT (\~) : inverse tous les bits.
  Exemple (8 bits) : \~0000 1111 = 1111 0000

------------

Décalages

* x << n : décaler à gauche → multiplication par 2ⁿ.
  Exemple : 0001 1010 (26) << 2 = 0110 1000 (104)
* x >> n : décaler à droite → division par 2ⁿ.

  * Logique (remplit avec 0) : 0001 1010 >> 2 = 0000 0110 (6)
  * Arithmétique (copie du signe) : 1110 0000 (-32) >> 2 = 1111 1000 (-8)

------------

Masques

* Tester bit k : (x & (1 << k)) != 0
* Activer bit k : x |= (1 << k)
* Désactiver bit k : x &= \~(1 << k)
* Basculer bit k : x ^= (1 << k)
* Extraire un champ \[s..e] : ((x >> s) & ((1 << (e-s+1)) - 1))

Exemples rapides
A = 0x6D (0110 1101)
B = 0x53 (0101 0011)

A & B = 0100 0001 = 0x41 (65)
A | B = 0111 1111 = 0x7F (127)
A ^ B = 0011 1110 = 0x3E (62)
\~A    = 1001 0010 = 0x92 (146)

------------

## Exercices

Exercice 1
0xF0 & 0x3C = ?
1111 0000 & 0011 1100 = 0011 0000 = 0x30 (48)
AND conserve seulement les 1 communs.

Exercice 2
0b0101\_1010 ^ 0b0011\_0011 = ?
\= 0110 1001 = 0x69 (105)
XOR = seuls les bits différents sont activés.

Exercice 3
x = 0b0001\_1010
x << 2 = 0110 1000 = 0x68 (104)
x >> 3 = 0000 0011 = 0x03 (3)
Décalage à gauche = ×4, à droite = ÷8.

Exercice 4
flags = 0b0000\_0000
Activer les bits 0 et 3 :
flags |= (1 << 0) | (1 << 3) = 0000 1001
Maintenant bit0 et bit3 sont activés.

Exercice 5
x = 0b1101\_0110
Extraire \[4..7] :
Masque = 1111 0000
(x & Masque) >> 4 = 1101 = 0xD (13)
Champ = 13.

Exercice 6
\~0b11110000 (8 bits) = 0000 1111 = 0x0F (15)
Inverse tous les bits.

Exercice 7
0b1010 | 0b0101 = ?
\= 1111 = 0xF (15)
OR combine les 1.

Exercice 8
x = 0b0010\_0100, tester bit2 :
Masque = 0000 0100
x & Masque = 0000 0100 ≠ 0 → vrai
Bit2 est activé.

Exercice 9
x = 0b0000\_0110
Basculer bit1 :
Masque = 0000 0010
x ^ Masque = 0000 0100
Bit1 basculé.

Exercice 10
x = 0b1010\_1101
Extraire 3 bits \[2..4] :
Décaler à droite de 2 → 0010 1011
Masque 0000 0111 → 0000 0011 = 3
Champ = 3.

------------

## Checklist

* Je sais appliquer AND/OR/XOR/NOT sur des octets.
* Je comprends la différence >> logique vs arithmétique.
* Je sais tester/activer/désactiver/basculer un bit avec un masque.
* Je peux extraire un champ multi-bit et le réaligner.
