# Block 02 · Audio Validation

**Status:** PASS_WITH_WARNINGS

## Vollständigkeit

- Erwartete Segmente: 70
- Erzeugte Segmente: 70
- Fehlende Segmente: 0
- Zusätzliche Segmente: 0
- Technische FAILs: 0

## Audio-Standard

- Quelle: Storyline-MP3 + Storyline-VTT
- Ausgabe: MP3, 44,1 kHz, mono, CBR 96 kbit/s
- Segmentierung: semantischer VTT-Abgleich gegen Expected Index; Schnitt anschließend innerhalb der realen Sprechpause auf ein lokales RMS-Minimum gelegt
- Pausen werden an internen Segmentgrenzen geteilt; dadurch bleiben Satzanfang/-ende vollständig und direkte App-Übergänge natürlich
- 3-ms-Mikrofade ausschließlich an bereits stillen Clipkanten als Klickschutz
- Keine Kompression, kein EQ, kein Noise Gate, kein Hall
- Lautheitsangleichung mit derselben Serienkalibrierung wie Block 01: Nichalia -3.65 dB, Bill -0.50 dB
- Abgeleitete Serienlautheit nach dem fixen Gain (aus EBU-R128-Messung der Storyline-Quellen): Nichalia ca. -18.69 LUFS, Bill ca. -18.78 LUFS
- Abgeleiteter True Peak nach dem fixen Gain: Nichalia ca. -3.58 dBTP, Bill ca. -1.71 dBTP

## Schnitt-QA

- Geprüfte interne Schnittgrenzen: 58
- Schlechtester RMS-Wert am Schnittpunkt: -77.7 dBFS
- Median RMS am Schnittpunkt: -84.6 dBFS
- Schnitt-WARNs (> −45 dBFS): 0

## Durchschnittliche Clipdauer

- QUESTION: 35.22 s
- RESPONSE: 17.24 s
- BOARD: 86.10 s
- TRANSFER: 16.66 s

## VTT ↔ Expected-Index

- Segmente technisch eindeutig zugeordnet: 70/70
- Segmente mit VTT-Text-WARN: 25
- WARN bedeutet: Segmentzuordnung und Schnitt sind sicher; Storyline-VTT hat aber einzelne Schreib-/Ausspracheformen gegenüber dem Solltext verändert oder tokenisiert. Die MP3 wird nicht inhaltlich manipuliert.

### Auffällige VTT-Varianten

- B02_Q12_QUESTION (100.00%): `dom änderungen` → `domänderungen`; `genai` → `gen ai`; `dom änderungen` → `domänderungen`
- B02_Q13_QUESTION (99.75%): `genai` → `gen ai`; `neupriorisierung` → `neuprisierung`
- B02_Q14_QUESTION (98.44%): `drei` → `3`; `few` → `vw`; `prompt verkettung` → `promptverkettung`
- B02_Q16_QUESTION (100.00%): `a b` → `ab`; `basis prompt` → `basisprompt`; `prompt anpassung` → `promptanpassung`
- B02_Q11_RESPONSE_S1 (100.00%): `testrealisierung` → `test realisierung`
- B02_Q11_RESPONSE_S2 (100.00%): `genai` → `gen ai`
- B02_Q11_BOARD (100.00%): `genai` → `gen ai`; `genai` → `gen ai`
- B02_Q12_BOARD (99.90%): `dom` → `dm`; `genai` → `gen ai`; `soll` → `sol`
- B02_Q13_BOARD (100.00%): `genai` → `gen ai`
- B02_Q14_RESPONSE_S1 (100.00%): `few shot` → `fewshot`
- B02_Q14_RESPONSE_S2 (100.00%): `prompt verkettung` → `promptverkettung`
- B02_Q14_RESPONSE_S3 (99.73%): `meta` → `met`
- B02_Q14_BOARD (99.71%): `acht` → `8`; `prompt verkettung` → `promptverkettung`; `few shot` → `fewshot`; `meta` → `met`
- B02_Q14_TRANSFER (100.00%): `prompt verkettung` → `promptverkettung`
- B02_Q15_BOARD (100.00%): `ein metrik` → `einmetrik`
- B02_Q16_RESPONSE_S1 (100.00%): `a b` → `ab`
- B02_Q16_RESPONSE_S4 (100.00%): `testerfeedback` → `tester feedback`; `a b` → `ab`
- B02_Q16_BOARD (100.00%): `zwei beliebige` → `zweibeliebige`
- B02_Q17_BOARD (99.11%): `siebzehn` → `17`; `risikodiagnose vier` → `risik diagnose 4`; `bias` → `bes`
- B02_Q18_RESPONSE_S1 (99.29%): `bias` → `bes`
- B02_Q18_BOARD (99.95%): `genau so` → `genauso`; `diagnosehilfe` → `diagnoseilfe`
- B02_Q19_RESPONSE_S1 (99.79%): `solche` → `solcher`
- B02_Q19_BOARD (99.52%): `neunzehn` → `19`
- B02_Q20_RESPONSE_S1 (99.24%): `token auswahl` → `tokuswahl`
- B02_Q20_RESPONSE_S3 (99.48%): `token` → `tok`

## Ergebnis

Alle 70 MP3-Segmente sind vorhanden, einheitlich codiert und für die Integration strukturiert. VTT-Abweichungen wurden transparent im Manifest dokumentiert; sie beeinträchtigen die sichere Segmentzuordnung nicht.

BLOCK_02_READY_FOR_INTEGRATION_WITH_VTT_WARNINGS