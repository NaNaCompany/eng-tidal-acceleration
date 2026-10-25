# 조석 차등가속도 계산기

같은 반지름 방향에 놓인 두 점이 받는 뉴턴 중력가속도의 크기 차를 계산한다.

- ID: E103
- App: https://nanalab.kr/eng-tidal-acceleration/
- Repository: https://github.com/NaNaCompany/eng-tidal-acceleration
- Formula: Δg = GM(1/r₁² − 1/r₂²)

## Model and data

M>0, r₂≥r₁>0. 두 점은 천체의 같은 쪽 반지름 방향이며 모두 구대칭 천체 바깥에 있어야 한다. 중심거리를 입력한다. 앱은 약한장 근사 범위를 r_s/r₁≤0.01로 제한한다. 차등가속도이며 힘·응력·삼차원 조석 텐서는 아니다. 자전·다른 천체·물체 내부 응답을 제외한다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
