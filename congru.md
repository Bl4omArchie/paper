# Congruence

Ce notebook est un cours sur les congruence, sujet introduit en arithmétique modulaire. Nous définirons ce qu'est une congruence ainsi que que ses propriétés et nous verrons un cas d'application avec le théorème des restes chinois ainsi qu'un exemple.

## Définition:

Historiquement, la notion de congruence sur les entiers relatifs a été introduite par Gauss vers 1801. Les congruences sont très utiles car elles permettent de ramener des calculs avec de très grands nombres à des calculs avec des nombres raisonnables
En arithmétique modulaire, on dit que deux entiers relatifs a et b sont congrus modulo n, avec n $ \in \mathbb{N} $, si et seulement a et b ont le même reste de la division euclidienne par n. Autrement dit, si a modulo n et b modulo n sont égaux, alors a et b sont congru. On peut donc aussi dire qu'ils sont congrus modulo n si leur différence est un multiple de n.

exemple:
```
a = 18, b = 23 et n = 5
18 mod 5 = 3
23 mod 5 = 3
Le reste de 18 et 23 divisé par 5 sont identiques, a et b sont donc congru 
On note alors: a ≡ b [n] 
```


## Propriétés:

### 1- Relation d'équivalence

Dans un ensemble, des éléments similaires du à certaines propriétés sont regroupés et l'on emploit la notion de classe d'équivalence.
Voici donc les relations d'équivalences parmis les congruences:
- réflexivité: $ \forall  a \in \mathbb{N} $, a ≡ a [n]
- symétrie: $ \forall  a, b \in \mathbb{N} $ a ≡ b [n] $\iff$ b ≡ a [n]
- transitivité: $ \forall a,b, c \in \mathbb{N} $ si a ≡ b [n] et b ≡ c [n] alors a ≡ c [n]

### 2- Propriétés algébriques

- si a ≡ b [n] et c ≡ d [n] alors $ c + d ≡  b + d [n] $
- si a ≡ b [n], alors $ \forall k \in \mathbb{Z} $: $k * a ≡ k * b [n] $
- si a ≡ b [n] et c ≡ d [n] alors $a * c ≡ b * d [n] $ 
- $ \forall k \in \mathbb{N} $: $a^k ≡ b^k [n]$

### 3- Théorème des restes chinois

La forme originale du théorème apparait sous forme de problème dans le livre de Sun Zi, le Sunzi suanjing, datant du IIIe siècle. Il est repris par le mathématicien chinois Qin Jiushao dans son ouvrage le Shùshū Jiǔzhāng (« Traité mathématique en neuf chapitres ») publié en 1247. Le résultat concerne les systèmes de congruences (voir arithmétique modulaire).
Selon Ulrich Libbrecht, la motivation de ce type de calcul chez les Chinois serait l'astronomie. On peut en effet penser que les Chinois, férus de calculs astronomiques, puissent être intéressés par des concordances de calendrier et qu'ils aient été amenés très tôt à s'intéresser à des questions du type :

Dans combien de jours la pleine lune tombera-t-elle au solstice d'hiver ?

Si la question se pose alors qu'il reste 6 jours avant le solstice d'hiver et 3 jours avant la pleine lune, la question se traduit par :

Existe-t-il un entier x tel que le reste de la division de x par 365 donne 6 et le reste de la division de x par 28 donne 3 ?

Soient $ m_1, m_2... m_n $ entiers premiers deux à deux entre eux ainsi que $ a_1, a_2... a_n $ entiers naturels non nuls.
Nous cherchons un entier N tel que: 
$$N ≡ a_1 [m_1] $$
$$N ≡ a_2 [m_2] $$
$$...           $$
$$N ≡ a_n [m_n] $$

Nous avons aussi $ m = m_1 * m_2 ... *  m_n $

Ansi, avec $j \in [1, n]$, on a $pgcd(\dfrac{m}{m_j}; m_j)$ = 1. D'après le théorème de Bézout (la fameux inverse modulaire: https://fr.wikipedia.org/wiki/Th%C3%A9or%C3%A8me_de_Bachet-B%C3%A9zout), on a $b_j$ tel que: $$ \dfrac{m}{m_j}*b_j ≡ 1 [m_j]; $$

$$
soit: \dfrac{m}{m_j}*b_j * a_j ≡ a_j [m_j] $$

Ce que l'on peut résumer par 
$$
x_0 = (\sum_{j=1}^{N} \dfrac{m}{m_j} * b_j * a_j) [m_i]
$$

#### Exemple:

$$x ≡ 3 [17]$$

$$x ≡ 4 [11]$$

$$x ≡ 5 [6]$$

Calculons d'abord $m = 3 * 4 * 5 = 60$. Il faut alors trouver une solution à chacune de ces congruences:

$$\dfrac{60}{3} * b_1 ≡ 1 [3]$$

$$\dfrac{60}{4} * b_1 ≡ 1 [4]$$

$$\dfrac{60}{5} * b_1 ≡ 1 [5]$$

On obtient alors: $b_1 = 2; b_2 = 3$ et $b_3 = 3$; Alors: 
$$
x_0 = (20 * 2 * 2) + (15 * 3 * 1) + (12 * 3 * 3) = 233
$$

Donc $x = 233 [60] = 53$, ce qui nous donne: 
$$ 53 ≡ 2 [3] $$

$$ 53 ≡ 1 [4] $$
$$...$$

On peut trouver toutes les autres solutions avec $x = 53 + 60 * k$ avec $k \in \mathbb{Z}$
