# Registro de decisões — Guia de Locais e Eventos (Mogi das Cruzes)

## Tipografia — clamp(mínimo, preferido, máximo), base 16px
| Elemento | Regra | ~360px | ~1280px |
|---|---|---|---|
| h1 da vitrine | `clamp(1.75rem, 6vw, 3rem)` | 6vw = 21,6px < 28px → **28px** (piso) | 6vw = 76,8px > 48px → **48px** (teto) |
| h1 da página do local | `clamp(1.5rem, 5vw, 2.5rem)` | 5vw = 18px < 24px → **24px** (piso) | 5vw = 64px > 40px → **40px** (teto) |
| Espaçamento das seções | `clamp(1rem, 4vw, 2rem)` | 14,4px → **16px** | **32px** |

## Mídia
- `img { max-width:100%; height:auto }` vale para qualquer imagem futura.
- `.card img { height:140px; object-fit:cover }` mantém a faixa do card sem deformar; `.capa` usa `aspect-ratio: 2/1`.
- `width`/`height` nos `<img>` evitam salto de layout.

## Usuário
- `<meta name="viewport" content="width=device-width, initial-scale=1">` nas 4 páginas (sem `user-scalable=no`).
- Links do menu, da lateral e da nav local com `min-height:44px`.
- `:focus-visible` com contorno de 3px em amarelo.
- `prefers-reduced-motion` desliga a rolagem suave; `prefers-color-scheme` adapta as cores.

## Layout (frente anterior)
- Cards: `repeat(auto-fit, minmax(min(230px,100%),1fr))` — quantidade sem media query.
- Desenho: base mobile-first (tudo empilhado); `@media (min-width:700px)` põe a lateral em 200px. Confirme o 700px encolhendo a janela na sua máquina e ajuste se falhar antes.

## Divisão: folha única × por página
| Página | Resolvido sozinho pelo `style.css` | Precisou de correção própria |
|---|---|---|
| index.html | topo, menu, cards, tipografia, foco, toque, rodapé | lateral "Explorar" e âncoras (#parques etc.); `aria-current` em "Início" |
| Páginas de local | topo, menu, rodapé, foco, toque, imagens | corpo com `class="detalhe"` (uma coluna, sem lateral); nav local (#sobre…); "Locais" com `.ativo` **sem** `aria-current`, pois o link aponta para a home |

## Auditoria Lighthouse (aba Acessibilidade) — PREENCHER após rodar
| Página | Nota | Achado (o que / onde) | Correção ou discordância |
|---|---|---|---|
| index.html | __ | | |
| parque-centenario.html | __ | | |
| museu-municipal.html | __ | | |
| teatro-vasconcelos.html | __ | | |

## Verificação
- [ ] Redimensionamento contínuo (home e locais) sem rolagem horizontal
- [ ] Emulação de celular: toque acerta os links, foco aparece no teclado
