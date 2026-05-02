<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Painel Sensi Yuri - VIP Webcord</title>
    <style>
        body { background-color: #050505; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
    </style>
</head>
<body>

<div id="painel-sensi" style="background: #0d0d0d; color: #fff; padding: 25px; border-radius: 20px; font-family: 'Segoe UI', sans-serif; max-width: 450px; border: 3px solid #00ff00; box-shadow: 0 0 15px rgba(0, 255, 0, 0.2); text-align: center; width: 90%;">
    
    <h1 style="font-size: 22px; color: #00ff00; text-transform: uppercase; letter-spacing: 2px; margin-bottom: 5px;">🎯 SENSI & DPI VIP YURI</h1>
    <p style="font-size: 13px; color: #888; margin-bottom: 25px;">Melhores configs para Webcord</p>
    
    <div style="margin-bottom: 25px;">
        <select id="select-celular" onchange="atualizarPainel()" style="width: 100%; padding: 12px; background: #1a1a1a; color: #fff; border: 2px solid #333; border-radius: 10px; font-weight: bold; cursor: pointer;">
            <option value="">📱 ESCOLHA SEU DISPOSITIVO</option>
            <option value="iphone">IPHONE (IOS)</option>
            <option value="samsung">SAMSUNG</option>
            <option value="xiaomi">XIAOMI / POCO</option>
            <option value="motorola">MOTOROLA</option>
            <option value="outros">OUTROS MODELOS</option>
        </select>
    </div>

    <div id="display-resultado" style="display: none; background: rgba(0, 255, 0, 0.05); padding: 20px; border-radius: 15px; border: 1px dashed #00ff00;">
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; text-align: left;">
            <div><span style="color: #888; font-size: 11px;">DPI</span><br><strong id="val-dpi" style="font-size: 18px; color: #fff;">-</strong></div>
            <div><span style="color: #888; font-size: 11px;">GERAL</span><br><strong id="val-geral" style="font-size: 18px; color: #fff;">-</strong></div>
            <div><span style="color: #888; font-size: 11px;">RED DOT</span><br><strong id="val-red" style="font-size: 18px; color: #fff;">-</strong></div>
            <div><span style="color: #888; font-size: 11px;">MIRA 2X</span><br><strong id="val-2x" style="font-size: 18px; color: #fff;">-</strong></div>
        </div>
        <hr style="border: 0; border-top: 1px solid #333; margin: 20px 0;">
        <p style="font-size: 12px; color: #00ff00; margin-bottom: 10px;">💎 Quer a Sensi VIP (R$ 2,00)?</p>
        <a href="https://discord.gg/U5fvUjYy4" target="_blank" style="display: block; background: #5865F2; color: white; text-decoration: none; padding: 12px; border-radius: 8px; font-weight: bold; text-transform: uppercase;">
            📩 ABRIR TICKET NO DISCORD
        </a>
    </div>
</div>

<script>
function atualizarPainel() {
    const dispositivo = document.getElementById('select-celular').value;
    const display = document.getElementById('display-resultado');
    const config = {
        'iphone': {dpi: 'Padrão', geral: '98', red: '95', x2: '100'},
        'samsung': {dpi: '600', geral: '95', red: '85', x2: '92'},
        'xiaomi': {dpi: '720', geral: '92', red: '90', x2: '88'},
        'motorola': {dpi: '580', geral: '100', red: '94', x2: '96'},
        'outros': {dpi: '500', geral: '100', red: '100', x2: '100'}
    };
    if (dispositivo) {
        const data = config[dispositivo];
        document.getElementById('val-dpi').innerText = data.dpi;
        document.getElementById('val-geral').innerText = data.geral;
        document.getElementById('val-red').innerText = data.red;
        document.getElementById('val-2x').innerText = data.x2;
        display.style.display = 'block';
    } else { display.style.display = 'none'; }
}
</script>
</body>
</html>
