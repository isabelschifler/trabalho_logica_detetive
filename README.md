# Detetive: O Caso da Cláusula Vazia

## Resumo dos resultados

| Dossiê | Tipo | Resultado |
|---|---|---|
| 1. O Álibi do Relógio | 
| 2. A Pegada no Jardim | 
| 3. O Cofre do Museu | 
| 4. O Testemunho Contraditório | 
| 5. O Suspeito Invisível |

---

## Dossiê 1: O Álibi do Relógio

**Símbolos**

- `R`: o relógio parou às 22h
- `L`: a luta foi às 22h
- `S`: o suspeito estava na sala às 22h
- `B`: o suspeito estava no baile às 22h

**Cláusulas**

1. `{¬R, L}`
2. `{R}`
3. `{¬L, S}`
4. `{B}`
5. `{¬S, ¬B}`, pois "ninguém está nos dois lugares" é `¬(S ∧ B) ≡ ¬S ∨ ¬B` (De Morgan)

**Resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (1) e (2) | `R` | (6) `{L}` |
| 2 | (6) e (3) | `L` | (7) `{S}` |
| 3 | (7) e (5) | `S` | (8) `{¬B}` |
| 4 | (8) e (4) | `B` | `□` |



## Dossiê 2: A Pegada no Jardim

**Símbolos**

- `C`: choveu à noite
- `M`: a terra do jardim estava molhada
- `P`: há pegada de bota no jardim
- `G`: o jardineiro passou pelo jardim depois da chuva

**Cláusulas**

1. `{¬C, M}`
2. `{C}`
3. `{¬P, ¬M, G}`, pois `(P ∧ M) → G ≡ ¬P ∨ ¬M ∨ G`
4. `{P}`
5. `{¬G}`, a negação da conclusão

**Resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (1) e (2) | `C` | (6) `{M}` |
| 2 | (3) e (4) | `P` | (7) `{¬M, G}` |
| 3 | (7) e (6) | `M` | (8) `{G}` |
| 4 | (8) e (5) | `G` | `□` |

**Conclusão:** surgiu `□`, então a conclusão está provada por refutação: o jardineiro passou pelo jardim depois da chuva. Isso mostra que ele passou por lá, não que é culpado.

---

## Dossiê 3: O Cofre do Museu

**Símbolos**

- `K`: o cofre foi aberto com a chave
- `F`: o cofre foi arrombado
- `A`: o alarme foi desativado
- `S`: o segurança estava de plantão

**Cláusulas**

1. `{K, F}`
2. `{¬F, A}`
3. `{S}`
4. `{¬A, ¬S}`
5. `{¬F}`, a negação da conclusão "foi arrombado"

**Resolução**

| Passo | Cláusulas | Literal cancelado | Resolvente |
|---|---|---|---|
| 1 | (2) e (4) | `A` | (6) `{¬F, ¬S}` |
| 2 | (6) e (3) | `S` | `{¬F}`, já existe em (5) |
| 3 | (1) e (5) | `F` | (7) `{K}` |
| 4 | (1) e (2) | `F` | (8) `{K, A}`, nada novo |

Depois disso nenhum cruzamento gera cláusula nova (saturação), e `□` não apareceu.

**Conclusão:** satisfatível. As pistas **não** provam o arrombamento.

**Valoração que satisfaz tudo:** `K = V`, `F = F`, `A = F`, `S = V`.

**Na história:** o cofre foi aberto com a chave, o alarme não foi desativado e o segurança estava de plantão. As pistas até apontam para `¬F`, contrariando o chefe da segurança.

---
