# Anti-fraud sistema — E2E demonstracija su GPT

Šis repo demonstruoja minimalų end-to-end fraud aptikimo srautą, naudojant:
- `data/X.csv` — sintetinių transakcijų požymiai
- `data/y.csv` — etiketės: 1 (fraud) / 0 (not_fraud)
- `prompts/test_prompt.txt` — testavimo prompt'as (griežtas JSON atsakymo formatas)
- `prompts/test_answer.txt` — pavyzdinis GPT atsakymas
- `assets/e2e_exampleN.json` — 3 demonstraciniai atvejai (įvestis → išvestis)

## Kaip per 30 sekundžių atkartoti prompt-testą
1. Nukopijuokite `prompts/test_prompt.txt` turinį.
2. Pateikite jį savo GPT agentui (pvz., ChatGPT) be pakeitimų.
3. Toliau pasirinkite pavyzdį.
4. Atsiųskite įvesties JSON testui patikrinkite, ar keičiasi sprendimas ir tikimybė.

## Duomenų laukai (`X.csv`)
- `transaction_id` — numeris
- `amount` — suma EUR
- `currency` — valiuta (EUR)
- `country` — šalis (ISO-2)
- `device_trust` — įrenginio pasitikėjimo lygis (`trusted|new_device|unknown`)
- `ip_risk` — IP rizikos balas [0..1]
- `time_hour` — paros valanda [0..23]
- `velocity_tx_last_24h` — transakcijų skaičius per paskutines 24h
- `merchant_type` — prekybininko tipas

## Pastabos
- Duomenys yra sintetiniai.
- Modelio vaidmenį atlieka GPT agentas, atsakymas privalo būti **griežtu JSON** formatu.
