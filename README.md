# Detetive: O Caso da Cláusula Vazia

## Resumo dos resultados

| Dossiê | Tipo | Resultado |
|---|---|---|
| 1. O Álibi do Relógio | Encadeamento de implicações | Insatisfatível |
| 2. A Pegada no Jardim | Prova por refutação | Conclusão provada |
| 3. O Cofre do Museu | Sem contradição | Satisfatível |
| 4. O Testemunho Contraditório | Depoimentos incompatíveis | Insatisfatível |
| 5. O Suspeito Invisível | Caso curto | Conclusão provada |

---

## Dossiê 1: O Álibi do Relógio

**DOSSIÊ:** O Álibi do Relógio   **DUPLA:** __________________

**1. Símbolos**

- `R`: o relógio parou às 22h
- `L`: a luta foi às 22h
- `S`: o suspeito estava na sala às 22h
- `B`: o suspeito estava no baile às 22h

**2. Pistas em lógica proposicional**

(P1) `R → L`   (P2) `R`   (P3) `L → S`   (P4) `B`   (P5) `¬(S ∧ B)`

**3. Conversão para FNC (com a equivalência usada)**

- P1: `R → L ≡ ¬R ∨ L`
- P3: `L → S ≡ ¬L ∨ S`
- P5: `¬(S ∧ B) ≡ ¬S ∨ ¬B` (De Morgan)
- P2 e P4 já são cláusulas unitárias.

**4. Conjunto de cláusulas (numeradas)**

(1) `{¬R, L}`   (2) `{R}`   (3) `{¬L, S}`   (4) `{B}`   (5) `{¬S, ¬B}`

Negação da conclusão, se houver: não há (o caso pede para verificar se as pistas são compatíveis).

**5. Passos de resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (1) e (2) | `R` | (6) `{L}` |
| 2 | (6) e (3) | `L` | (7) `{S}` |
| 3 | (7) e (5) | `S` | (8) `{¬B}` |
| 4 | (8) e (4) | `B` | `□` |

**6. Conclusão**

- [x] Cláusula vazia encontrada: **INSATISFATÍVEL**
- [ ] Sem cláusula vazia: SATISFATÍVEL

O que isso significa no caso: o álibi do suspeito não é compatível com as outras pistas. Alguém errou ou mentiu.

---

## Dossiê 2: A Pegada no Jardim

**DOSSIÊ:** A Pegada no Jardim   **DUPLA:** __________________

**1. Símbolos**

- `C`: choveu à noite
- `M`: a terra do jardim estava molhada
- `P`: há pegada de bota no jardim
- `G`: o jardineiro passou pelo jardim depois da chuva

**2. Pistas em lógica proposicional**

(P1) `C → M`   (P2) `C`   (P3) `(P ∧ M) → G`   (P4) `P`

Conclusão a investigar: `G`

**3. Conversão para FNC (com a equivalência usada)**

- P1: `C → M ≡ ¬C ∨ M`
- P3: `(P ∧ M) → G ≡ ¬(P ∧ M) ∨ G ≡ ¬P ∨ ¬M ∨ G` (implicação e De Morgan)
- P2 e P4 já são cláusulas unitárias.

**4. Conjunto de cláusulas (numeradas)**

(1) `{¬C, M}`   (2) `{C}`   (3) `{¬P, ¬M, G}`   (4) `{P}`

Negação da conclusão, se houver: (5) `{¬G}`

**5. Passos de resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (1) e (2) | `C` | (6) `{M}` |
| 2 | (3) e (4) | `P` | (7) `{¬M, G}` |
| 3 | (7) e (6) | `M` | (8) `{G}` |
| 4 | (8) e (5) | `G` | `□` |

**6. Conclusão**

- [x] Cláusula vazia encontrada: **INSATISFATÍVEL** (com `¬G` incluída)
- [ ] Sem cláusula vazia: SATISFATÍVEL

O que isso significa no caso: a conclusão está provada por refutação. O jardineiro passou pelo jardim depois da chuva. Isso não prova que ele é culpado.

---

## Dossiê 3: O Cofre do Museu

**DOSSIÊ:** O Cofre do Museu   **DUPLA:** __________________

**1. Símbolos**

- `K`: o cofre foi aberto com a chave
- `F`: o cofre foi arrombado
- `A`: o alarme foi desativado
- `S`: o segurança estava de plantão

**2. Pistas em lógica proposicional**

(P1) `K ∨ F`   (P2) `F → A`   (P3) `S`   (P4) `¬A ∨ ¬S`

Conclusão a investigar: `F` (o cofre foi arrombado)

**3. Conversão para FNC (com a equivalência usada)**

- P2: `F → A ≡ ¬F ∨ A`
- P1, P3 e P4 já estão em forma de cláusula.

**4. Conjunto de cláusulas (numeradas)**

(1) `{K, F}`   (2) `{¬F, A}`   (3) `{S}`   (4) `{¬A, ¬S}`

Negação da conclusão, se houver: (5) `{¬F}`

**5. Passos de resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (2) e (4) | `A` | (6) `{¬F, ¬S}` |
| 2 | (6) e (3) | `S` | `{¬F}` (já existe em (5)) |
| 3 | (1) e (5) | `F` | (7) `{K}` |
| 4 | (1) e (2) | `F` | (8) `{K, A}` (nada de novo) |

Depois disso nenhum cruzamento gera cláusula nova (saturação).

**6. Conclusão**

- [ ] Cláusula vazia encontrada: INSATISFATÍVEL
- [x] Sem cláusula vazia: **SATISFATÍVEL** (valoração: `K = V`, `F = F`, `A = F`, `S = V`)

O que isso significa no caso: as pistas não provam o arrombamento. Elas indicam que o cofre foi aberto com a chave, o alarme não foi desativado e o segurança estava de plantão, contrariando o chefe da segurança.

---

## Dossiê 4: O Testemunho Contraditório

**DOSSIÊ:** O Testemunho Contraditório   **DUPLA:** __________________

**1. Símbolos**

- `P`: ele saiu pela porta dos fundos
- `J`: ele saiu pela janela
- `C`: a câmera dos fundos o registrou

**2. Pistas em lógica proposicional**

(P1) `P ∨ J`   (P2) `¬J`   (P3) `P → C`   (P4) `¬C`

**3. Conversão para FNC (com a equivalência usada)**

- P3: `P → C ≡ ¬P ∨ C`
- P1, P2 e P4 já estão em forma de cláusula.

**4. Conjunto de cláusulas (numeradas)**

(1) `{P, J}`   (2) `{¬J}`   (3) `{¬P, C}`   (4) `{¬C}`

Negação da conclusão, se houver: não há.

**5. Passos de resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (1) e (2) | `J` | (5) `{P}` |
| 2 | (5) e (3) | `P` | (6) `{C}` |
| 3 | (6) e (4) | `C` | `□` |

**6. Conclusão**

- [x] Cláusula vazia encontrada: **INSATISFATÍVEL**
- [ ] Sem cláusula vazia: SATISFATÍVEL

O que isso significa no caso: os quatro depoimentos não podem ser todos verdadeiros. Pelo menos uma fonte mente ou se engana.

---

## Dossiê 5: O Suspeito Invisível

**DOSSIÊ:** O Suspeito Invisível   **DUPLA:** __________________

**1. Símbolos**

- `S`: o suspeito estava no local
- `D`: o suspeito usou disfarce
- `W`: foram deixados fios de peruca

**2. Pistas em lógica proposicional**

(P1) `S ∨ D`   (P2) `D → W`   (P3) `¬W`

Conclusão a investigar: `S`

**3. Conversão para FNC (com a equivalência usada)**

- P2: `D → W ≡ ¬D ∨ W`
- P1 e P3 já estão em forma de cláusula.

**4. Conjunto de cláusulas (numeradas)**

(1) `{S, D}`   (2) `{¬D, W}`   (3) `{¬W}`

Negação da conclusão, se houver: (4) `{¬S}`

**5. Passos de resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (2) e (3) | `W` | (5) `{¬D}` |
| 2 | (1) e (5) | `D` | (6) `{S}` |
| 3 | (6) e (4) | `S` | `□` |

**6. Conclusão**

- [x] Cláusula vazia encontrada: **INSATISFATÍVEL** (com `¬S` incluída)
- [ ] Sem cláusula vazia: SATISFATÍVEL

O que isso significa no caso: a conclusão está provada. Sem fios de peruca, não houve disfarce, então o suspeito esteve no local e não é invisível.

---
