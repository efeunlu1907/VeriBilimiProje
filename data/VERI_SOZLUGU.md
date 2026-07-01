# Veri Sözlüğü

**Veri seti:** İngiltere Premier Lig maç istatistikleri (2020-21 → 2023-24, 4 sezon × 380 maç).
**Kaynak:** [datasets/football-datasets](https://github.com/datasets/football-datasets)
(orijinal: [football-data.co.uk](https://www.football-data.co.uk/)).
**Lisans:** Open Data Commons Public Domain Dedication and License (PDDL) v1.0.

Her satır bir maçı temsil eder. Sütunlar:

| Sütun | Açıklama |
| ----- | -------- |
| `Date` | Maç tarihi |
| `HomeTeam` | Ev sahibi takım |
| `AwayTeam` | Deplasman takımı |
| `FTHG` | Maç sonu ev sahibi gol sayısı (Full Time Home Goals) |
| `FTAG` | Maç sonu deplasman gol sayısı (Full Time Away Goals) |
| `FTR` | Maç sonucu: **H** = ev galibiyeti, **D** = beraberlik, **A** = deplasman galibiyeti |
| `HTHG` | İlk yarı ev sahibi gol sayısı (Half Time Home Goals) |
| `HTAG` | İlk yarı deplasman gol sayısı (Half Time Away Goals) |
| `HTR` | İlk yarı sonucu (H / D / A) |
| `Referee` | Maçın hakemi |
| `HS` / `AS` | Ev / deplasman toplam şut (Home/Away Shots) |
| `HST` / `AST` | Ev / deplasman isabetli şut (Shots on Target) |
| `HF` / `AF` | Ev / deplasman faul sayısı (Fouls) |
| `HC` / `AC` | Ev / deplasman korner sayısı (Corners) |
| `HY` / `AY` | Ev / deplasman sarı kart (Yellow cards) |
| `HR` / `AR` | Ev / deplasman kırmızı kart (Red cards) |

## Notebook'ta türetilen sütunlar

Aşağıdaki sütunlar ham veride yoktur; analiz/temizleme adımında oluşturulur:

| Sütun | Tanım |
| ----- | ----- |
| `Season` | Dosya adından eklenen sezon etiketi (ör. `2022-2023`) |
| `TotalGoals` | `FTHG + FTAG` (maçtaki toplam gol) |
| `GoalDiff` | `FTHG - FTAG` (ev sahibi bakış açısıyla gol farkı) |
| `HomeWin` | Ev sahibi kazandıysa 1, aksi halde 0 |
| `SoTDiff` | `HST - AST` (isabetli şut farkı) |
| `ShotsDiff` | `HS - AS` (toplam şut farkı) |
| `CornersDiff` | `HC - AC` (korner farkı) |
| `FoulsDiff` | `HF - AF` (faul farkı) |
| `YellowDiff` | `HY - AY` (sarı kart farkı) |
| `RedDiff` | `HR - AR` (kırmızı kart farkı) |
| `HTGoalDiff` | `HTHG - HTAG` (ilk yarı gol farkı) |
