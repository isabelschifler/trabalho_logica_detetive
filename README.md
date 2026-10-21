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

**Conclusão:** insatisfatível. O álibi do suspeito não é compatível com as outras pistas: ou os convidados erraram, ou o relógio enganou.

---
