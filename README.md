# Penosa Desktop Sim

Simulador desktop da Penosa para PC, feito em HTML/CSS/JavaScript.

## O que ele replica

- Algoritmo euclidiano da Penosa com a mesma logica de `steps`, `hits`, `rotation` e `auto-rotate downbeat`
- Visualizacao concentrica dos circulos no estilo do display
- BassGroove com `density`, `range`, `scale` e `root`
- Slots de preset com persistencia em `localStorage`
- Audio via WebAudio com sintese mais proxima das vozes do firmware (`KickVoice`, `SnareVoice`, `HatsVoice`, `BassVoice`)
- Laboratorio de algoritmo com seed deterministica, step manual, export/import de estado e debug do `BassGroove`
- Edicao de voz por track com controles de tune, decay, timbre, drive, snap, harmonics e modo de snare

## Como rodar

Opcao 1:

- Abra `index.html` diretamente no navegador

Opcao 2:

```powershell
cd "C:\Users\devx\Documents\PlatformIO\Projects\Penosa DM\desktop-penosa-sim"
python -m http.server 8080
```

Depois abra:

- [http://localhost:8080](http://localhost:8080)

## Controles

- `Space`: play/stop
- `Right Arrow`: avanca um step quando o transporte estiver parado
- `1..5`: troca de track
- `Play`: inicia o transporte
- `Step`: executa um tick manual do algoritmo
- `Randomize`: varia os pads euclidianos
- `Apply Seed`: fixa a seed para reproduzir variacoes e testes
- `Export/Import State`: salva e restaura snapshots completos do experimento
- `Save Slot`: salva o estado atual no slot selecionado
- `Voice DSP`: edita a sintese da track selecionada

## Observacoes

- O audio aqui ainda e uma aproximacao desktop, mas agora segue mais de perto as formulas e envelopes do firmware ESP32.
- A visualizacao foi portada da logica do `drawPerformanceView()` da Penosa.
- O painel `Debug` mostra a ultima decisao do baixo, o log recente de eventos e os pads euclidianos com `steps/hits/rotation`.
