# Aeroportos Monitorados

Lista dos aeroportos configurados neste projeto para monitoramento de voos em tempo real via AviationStack API.

| ICAO | Aeroporto | Cidade | Estado |
|------|-----------|--------|--------|
| **SBCA** | Aeroporto Regional do Oeste | Cascavel | Paraná |
| **SBCT** | Aeroporto Internacional Afonso Pena | Curitiba | Paraná |
| **SBPA** | Aeroporto Internacional Salgado Filho | Porto Alegre | Rio Grande do Sul |

## Justificativa da Escolha

- **SBCA – Cascavel**: aeroporto base obrigatório conforme enunciado da atividade.
- **SBCT – Curitiba (Afonso Pena)**: maior aeroporto do Paraná, com alto volume de voos domésticos e internacionais, relevante para análise regional.
- **SBPA – Porto Alegre (Salgado Filho)**: principal hub do Sul do Brasil, conecta a região com destinos nacionais e internacionais.

## Configuração no GitHub Actions

Os aeroportos são definidos pela variável de ambiente `AIRPORTS` no workflow `.github/workflows/update-flights.yml`:

```
AIRPORTS: SBCA,SBCT,SBPA
```

Os dados são atualizados automaticamente uma vez por dia (12h UTC) e salvos em `data/{ICAO}.json`.
