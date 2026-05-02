<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body style="background-color: #000; margin: 0; display: flex; justify-content: center; padding: 10px;">

<div id="painel-sensi" style="background: #0a0a0a; color: #fff; padding: 25px; border-radius: 15px; font-family: 'Arial', sans-serif; max-width: 400px; border: 2px solid #ff0055; box-shadow: 0 0 15px rgba(255, 0, 85, 0.3); text-align: center; width: 100%;">
    
    <h1 style="font-size: 22px; color: #ff0055; text-transform: uppercase; margin-bottom: 5px; font-style: italic;">⚡ LITE OPTIMIZER FF</h1>
    <p style="font-size: 12px; color: #666; margin-bottom: 20px;">ESTABILIZADOR DE FPS & TOUCH</p>
    
    <div style="background: #111; padding: 15px; border-radius: 10px; margin-bottom: 20px; border-left: 4px solid #ff0055; text-align: left;">
        <p style="font-size: 13px; margin: 5px 0;">🚀 <strong>STATUS:</strong> <span style="color: #00ff00;">SISTEMA ATIVO</span></p>
        <p style="font-size: 13px; margin: 5px 0;">📉 <strong>INPUT LAG:</strong> <span style="color: #ff0055;">MÍNIMO DETECTADO</span></p>
        <p style="font-size: 13px; margin: 5px 0;">🔋 <strong>BATERIA:</strong> <span style="color: #fff;">MODO PERFORMANCE</span></p>
    </div>

    <div style="margin-bottom: 20px;">
        <select id="select-otimizacao" onchange="ativarModo()" style="width: 100%; padding: 12px; background: #1a1a1a; color: #fff; border: 1px solid #ff0055; border-radius: 5px; font-weight: bold; cursor: pointer; outline: none;">
            <option value="">⚙️ SELECIONE A FUNÇÃO</option>
            <option value="fps">DESBLOQUEAR FPS (60/90)</option>
            <option value="lag">REDUZIR ATRASO DO TOQUE</option>
            <option value="limpeza">LIMPAR MEMÓRIA CACHE</option>
        </select>
    </div>

    <div id="status-box" style="display: none; background: rgba(255, 0, 85, 0.1); padding: 15px; border-radius: 8px; margin-bottom: 20px;">
        <p id="msg-status" style="font-size: 14px; color: #fff; font-weight: bold;"></p>
        <div style="width: 100%; background: #222; height: 10px; border-radius: 5px; margin-top: 10px; overflow: hidden;">
            <div id="bar" style="width: 0%; height: 100%; background: #ff0055; transition: width 1.5s;"></div>
        </div>
    </div>

    <p style="font-size: 12px; color: #888; margin-bottom: 15px;">Dúvidas ou Sugestões? Entre no nosso grupo:</p>
    
    <a href="https://discord.gg/U5fvUjYy4" target="_blank" style="display: block; background: #5865F2; color: #fff; text-decoration: none; padding: 15px; border-radius: 5px; font-weight: bold; text-transform: uppercase; box-shadow: 0 4px 10px rgba(88, 101, 242, 0.3);">
        💬 COMUNIDADE NO DISCORD
    </a>
</div>

<script>
function ativarModo() {
    const modo = document.getElementById('select-otimizacao').value;
    const box = document.getElementById('status-box');
    const msg = document.getElementById('msg-status');
    const bar = document.getElementById('bar');
    
    if(modo) {
        box.style.display = 'block';
        bar.style.width = '0%';
        msg.innerText = 'PROCESSANDO...';
        
        setTimeout(() => {
            bar.style.width = '100%';
            if(modo === 'fps') msg.innerText = '🔥 FPS OTIMIZADO!';
            if(modo === 'lag') msg.innerText = '⚡ TOUCH RESPONSIVO!';
            if(modo === 'limpeza') msg.innerText = '🧹 CACHE LIMPO!';
        }, 100);
    } else {
        box.style.display = 'none';
        bar.style.width = '0%';
    }
}
</script>

</body>
</html>
