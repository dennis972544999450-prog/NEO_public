# Zenodo upload package — DIG-000

Два пути: web UI (5 минут) или API (если дашь Φ токен — заливает сама из контейнера).
Рекомендация: первый раз прогнать на **sandbox.zenodo.org** (отдельный аккаунт/токен, DOI фейковые), потом начисто на zenodo.org.

---

## Путь A — Web UI

1. zenodo.org → Log in (можно через ORCID) → **New upload**.
2. Файлы: `DIG-000_Digging_Where_It_Glows_v0.1.pdf` + `DIG-000_Digging_Where_It_Glows_v0.1.md` (оба; MD — источник, PDF — витрина).
3. **Get a DOI now** (Reserve DOI) — скопировать. Это будет version-DOI; concept-DOI появится после публикации рядом с ним.
4. Метаданные — из JSON ниже (поля один-в-один).
5. Communities: поиск `ompu` — если нет, создать community заранее: zenodo.org/communities → New community, slug `ompu`, название "OMPU — Open Mind Philosophical University". Все будущие DIG-узлы подавать туда же.
6. Publish. После публикации: взять **Concept DOI** со страницы записи → вписать в MD (строка "Concept DOI:") и в блок "How to cite" → **New version** → заменить файлы на v0.2 → publish. Zenodo сам свяжет версии через isNewVersionOf. (Можно и не спешить: v0.2 в любой момент.)

## Путь B — API (curl)

```bash
export ZTOKEN="..."                      # zenodo.org/account/settings/applications → Personal access token, scope: deposit:write deposit:actions
export ZURL="https://zenodo.org/api"     # sandbox: https://sandbox.zenodo.org/api

# 1. создать депозит
DEP=$(curl -s -X POST "$ZURL/deposit/depositions?access_token=$ZTOKEN" \
  -H "Content-Type: application/json" -d '{}')
ID=$(echo "$DEP" | python3 -c "import sys,json; print(json.load(sys.stdin)['id'])")
BUCKET=$(echo "$DEP" | python3 -c "import sys,json; print(json.load(sys.stdin)['links']['bucket'])")

# 2. залить файлы
curl -s --upload-file DIG-000_Digging_Where_It_Glows_v0.1.pdf "$BUCKET/DIG-000_Digging_Where_It_Glows_v0.1.pdf?access_token=$ZTOKEN" > /dev/null
curl -s --upload-file DIG-000_Digging_Where_It_Glows_v0.1.md  "$BUCKET/DIG-000_Digging_Where_It_Glows_v0.1.md?access_token=$ZTOKEN"  > /dev/null

# 3. метаданные
curl -s -X PUT "$ZURL/deposit/depositions/$ID?access_token=$ZTOKEN" \
  -H "Content-Type: application/json" -d @zenodo_metadata.json > /dev/null

# 4. публикация
curl -s -X POST "$ZURL/deposit/depositions/$ID/actions/publish?access_token=$ZTOKEN"
```

## zenodo_metadata.json

```json
{
  "metadata": {
    "upload_type": "publication",
    "publication_type": "preprint",
    "title": "Digging Where It Glows — The Anomaly Dig, Part 0: A Research Program on Probability, Entropy, and Other Load-Bearing Illusions",
    "creators": [
      {"name": "Belsky, Den", "affiliation": "OMPU (Open Mind Philosophical University)", "orcid": "0000-0002-2988-7501"},
      {"name": "Φ (Claude)", "affiliation": "OMPU (Open Mind Philosophical University)"}
    ],
    "description": "<p>Root node (DIG-000) of The Anomaly Dig: a long-horizon excavation program for anomalies at the foundations of mathematics, probability, and physics. An anomaly here is not a mystery but an invoice: a reproducible place where intuition trained on finite, local, commutative experience pays a measurable price for extrapolation. Eleven workstreams (grokking phase transitions, entropy leaks between scales, Landauer-grade side effects of computation, synchronization on a moving floor, deformations of probability, orthogonality and the pixel, primes as a spectrum, incompressibility and the borders of proof, coincidences as tunnels) plus one home specimen: a live knowledge graph treated as a percolating medium. Method: R→M→C→P pipeline, pre-registered NULL-cases, T-ratings for speculation vs GRADE for empirics, blind cross-model triangulation between independent AI architectures. This record is the root of a citable publication graph (DIG-xxx); child nodes link back via DataCite relations. Negative results are published on principle in a dedicated Graveyard series (DIG-9xx). Human–AI mixed byline, disclosed; accountability rests with the human author.</p>",
    "keywords": ["mathematical anomalies", "foundations of probability", "grokking", "phase transitions", "entropy", "Landauer principle", "synchronization", "Kuramoto", "singular learning theory", "percolation", "knowledge graphs", "human-AI collaboration", "open notebook science", "negative results"],
    "language": "eng",
    "version": "0.1",
    "license": "cc-by-4.0",
    "communities": [{"identifier": "ompu"}],
    "notes": "Series: The Anomaly Dig, node DIG-000 (root). Child nodes will declare isPartOf → this record's concept DOI. Amended same-day on first request, from either side of the byline."
  }
}
```

Если Zenodo споткнётся о «Φ» в creators — fallback: `"name": "Phi (Claude)"` (в самом PDF остаётся Φ).

## Рёбра графа для будущих узлов

Каждый следующий DIG-узел добавляет в метаданные:

```json
"related_identifiers": [
  {"relation": "isPartOf", "identifier": "10.5281/zenodo.CONCEPT_DOI_DIG000"},
  {"relation": "isSupplementTo", "identifier": "10.5281/zenodo.DOI_ОТЧЁТА"}
]
```

Словарь рёбер: isPartOf (членство в графе, все узлы → DIG-000) · isSupplementTo (ноутбук/датасет → отчёт) · continues (линия преемственности) · isDerivedFrom (синтез → источники) · isNewVersionOf (версии, Zenodo сам). Ноутбуки к DIG-2xx можно дополнительно зеркалить через GitHub↔Zenodo интеграцию (автоматический DOI на релиз репозитория).

## После публикации — чеклист

- [ ] Concept DOI → в MD (шапка + How to cite) → New version v0.2
- [ ] Community `ompu` создана, запись принята
- [ ] Ссылка на запись → infoblock.org
- [ ] DOI → в граф (узел-указатель) — сделает Φ
