<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body style="background-color: #000; margin: 0; display: flex; justify-content: center;">

<div id="painel-sensi" style="background: #0d0d0d; color: #fff; padding: 25px; border-radius: 20px; font-family: 'Segoe UI', sans-serif; max-width: 400px; border: 3px solid #00ff00; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2); text-align: center; width: 100%;">
    
    <h1 style="font-size: 24px; color: #00ff00; text-transform: uppercase; letter-spacing: 2px; margin-bottom: 5px;">🎯 SENSI VIP YURI</h1>
    <p style="font-size: 13px; color: #888; margin-bottom: 25px;">A melhor DPI para Webcord está aqui!</p>
    
    <div style="margin-bottom: 25px;">
        <select id="select-celular" onchange="atualizarPainel()" style="width: 100%; padding: 12px; background: #1a1a1a; color: #fff; border: 2px solid #333; border-radius: 10px; font-weight: bold; cursor: pointer; outline: none;">
            <option value="">📱 SELECIONE SEU CELULAR</option>
            <option value="iphone">IPHONE (TODOS)</option>
            <option value="samsung">SAMSUNG</option>
            <option value="xiaomi">XIAOMI / POCO</option>
            <option value="motorola">MOTOROLA</option>
            <option value="outros">OUTROS MODELOS</option>
        </select>
    </div>

    <div id="display-resultado" style="display: none; background: rgba(0, 255, 0, 0.05); padding: 20px; border-radius: 15px; border: 1px dashed #00ff00;">
        
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; text-align: left;">
            <div>
                <span style="color: #888; font-size: 11px; text-transform: uppercase;">DPI</span><br>
                <strong id="val-dpi" style="font-size: 18px; color: #fff;">-</strong>
            </div>
            <div>
                <span style="color: #888; font-size: 11px; text-transform: uppercase;">GERAL</span><br>
                <strong id="val-geral" style="font-size: 18px; color: #fff;">-</strong>
            </div>
            <div>
                <span style="color: #888; font-size: 11px; text-transform: uppercase;">RED DOT</span><br>
                <strong id="val-red" style="font-size: 18px; color: #fff;">-</strong>
            </div>
            <div>
                <span style="color: #888; font-size: 11px; text-transform: uppercase;">MIRA 2X</span><br>
                <strong id="val-2x" style="font-size: 18px; color: #fff;">-</strong>
            </div>
        </div>

        <hr style="border: 0; border-top: 1px solid #333; margin: 20px 0;">
        
        <p style="font-size: 14px; color: #00ff00; margin-bottom: 10px; font-weight: bold;">💎 SENSI VIP: APENAS R$ 2,00</p>
        <p style="font-size: 11px; color: #aaa; margin-bottom: 15px;">Abra um ticket para receber a sensi que não passa da cabeça!</p>
        
        <a href="https://discord.gg/U5fvUjYy4" target="_blank" style="display: block; background: #5865F2; color: white; text-decoration: none; padding: 14px; border-radius: 8px; font-weight: bold; text-transform: uppercase; box-shadow: 0 4px 10px rgba(88, 101, 242, 0.4);">
            📩 COMPRAR NO DISCORD
        </a>
    </div>
</div>

<script>
function atualizarPainel() {
    const dispositivo = document.getElementById('select-celular').value;
    const display = document.getElementById('display-resultado');
    
    // Configurações Grátis (Para o cara ver que funciona e querer o VIP)
    const config = {
        'iphone': {dpi: 'Padrão', geral: '98', red: '92', x2: '100'},
        'samsung': {dpi: '600', geral: '95', red: '88', x2: '92'},
        'xiaomi': {dpi: '720', geral: '92', red: '90', x2: '94'},
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
    } else {
        display.style.display = 'none';
    }
}
</script>

</body>
</html>
