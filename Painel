<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { background-color: #000; margin: 0; font-family: 'Segoe UI', sans-serif; color: #fff; display: flex; justify-content: center; padding: 10px; }
        .container { background: #0a0a0a; width: 100%; max-width: 400px; border-radius: 20px; border: 2px solid #00ff00; overflow: hidden; box-shadow: 0 0 20px rgba(0, 255, 0, 0.2); }
        .tabs { display: flex; background: #111; border-bottom: 1px solid #333; }
        .tab-btn { flex: 1; padding: 15px; border: none; background: none; color: #666; font-weight: bold; cursor: pointer; text-transform: uppercase; font-size: 11px; }
        .tab-btn.active { color: #00ff00; border-bottom: 2px solid #00ff00; background: rgba(0, 255, 0, 0.05); }
        .content { padding: 15px; display: none; }
        .content.active { display: block; }
        select, button { width: 100%; padding: 12px; margin-top: 10px; border-radius: 8px; border: 1px solid #333; background: #1a1a1a; color: #fff; font-weight: bold; outline: none; }
        .res-box { background: #111; padding: 15px; border-radius: 10px; margin-top: 15px; border-left: 4px solid #00ff00; }
        .grid-sensi { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; text-align: left; margin-top: 10px; }
        .item-s { background: #1a1a1a; padding: 8px; border-radius: 5px; border: 1px solid #222; }
        .item-s small { color: #00ff00; font-size: 10px; text-transform: uppercase; }
        .item-s strong { display: block; font-size: 16px; margin-top: 2px; }
        .vip-card { background: linear-gradient(145deg, #1a1a1a, #000); border: 1px solid #ffeb3b; padding: 15px; border-radius: 10px; margin-top: 20px; text-align: center; }
        .bar-container { width: 100%; background: #222; height: 8px; border-radius: 4px; margin-top: 10px; overflow: hidden; display: none; }
        .bar { width: 0%; height: 100%; background: #00fbff; transition: width 1.5s; }
    </style>
</head>
<body>

<div class="container">
    <div class="tabs">
        <button class="tab-btn active" onclick="openTab(event, 'sensi')">🎯 Sensi Completa</button>
        <button class="tab-btn" onclick="openTab(event, 'otimizacao')">⚡ Otimização</button>
    </div>

    <div id="sensi" class="content active">
        <h2 style="font-size: 18px; color: #00ff00; margin-bottom: 5px; text-align: center;">⚙️ CONFIGURAÇÃO FREE</h2>
        
        <select id="dev-select" onchange="mostrarSensi()">
            <option value="">📱 ESCOLHER MEU CELULAR</option>
            <option value="iphone">IPHONE (TODOS)</option>
            <option value="samsung">SAMSUNG</option>
            <option value="xiaomi">XIAOMI</option>
            <option value="motorola">MOTOROLA</option>
        </select>

        <div id="box-sensi" class="res-box" style="display:none;">
            <div class="grid-sensi">
                <div class="item-s"><small>DPI</small><strong id="d-dpi">0</strong></div>
                <div class="item-s"><small>Geral</small><strong id="d-geral">0</strong></div>
                <div class="item-s"><small>Red Dot</small><strong id="d-red">0</strong></div>
                <div class="item-s"><small>Mira 2x</small><strong id="d-2x">0</strong></div>
                <div class="item-s"><small>Mira 4x</small><strong id="d-4x">0</strong></div>
                <div class="item-s"><small>Botão</small><strong>55%</strong></div>
            </div>
        </div>

        <div class="vip-card">
            <h3 style="color: #ffeb3b; font-size: 14px; margin: 0;">💎 SENSI VIP SUPREMA (R$ 2,00)</h3>
            <p style="font-size: 11px; color: #aaa; margin: 5px 0;">Regedit atualizada + Sensi Anti-Aceleramento</p>
            <a href="https://discord.gg/U5fvUjYy4" target="_blank" style="display: block; background: #ffeb3b; color: #000; text-decoration: none; padding: 10px; border-radius: 5px; font-weight: bold; font-size: 12px;">COMPRAR AGORA</a>
        </div>
    </div>

    <div id="otimizacao" class="content">
        <h2 style="font-size: 18px; color: #00fbff; margin-bottom: 5px; text-align: center;">⚡ PERFORMANCE</h2>
        <button onclick="carregar('fps')" style="border-color: #00fbff; color: #00fbff;">🚀 ATIVAR 90 FPS</button>
        <button onclick="carregar('lag')" style="border-color: #ff0055; color: #ff0055;">🕹️ TIRAR INPUT LAG</button>

        <div id="status-vip" style="margin-top: 20px; display: none;">
            <small id="status-msg" style="color: #00fbff; font-weight: bold; font-size: 11px;"></small>
            <div class="bar-container" style="display: block;"><div class="bar" id="b"></div></div>
        </div>
    </div>

    <div style="padding: 10px; text-align: center;">
        <a href="https://discord.gg/U5fvUjYy4" target="_blank" style="color: #5865F2; text-decoration: none; font-size: 12px; font-weight: bold;">ENTRAR NO DISCORD</a>
    </div>
</div>

<script>
    function openTab(evt, tabName) {
        var i, content, tablinks;
        content = document.getElementsByClassName("content");
        for (i = 0; i < content.length; i++) { content[i].style.display = "none"; }
        tablinks = document.getElementsByClassName("tab-btn");
        for (i = 0; i < tablinks.length; i++) { tablinks[i].className = tablinks[i].className.replace(" active", ""); }
        document.getElementById(tabName).style.display = "block";
        evt.currentTarget.className += " active";
    }

    function mostrarSensi() {
        const d = document.getElementById('dev-select').value;
        const b = document.getElementById('box-sensi');
        const c = { 
            'iphone':['Padrão','98','92','100','100'], 
            'samsung':['600','95','88','94','98'], 
            'xiaomi':['720','92','90','92','95'], 
            'motorola':['580','100','94','96','100'] 
        };
        if(d) {
            b.style.display = 'block';
            document.getElementById('d-dpi').innerText = c[d][0];
            document.getElementById('d-geral').innerText = c[d][1];
            document.getElementById('d-red').innerText = c[d][2];
            document.getElementById('d-2x').innerText = c[d][3];
            document.getElementById('d-4x').innerText = c[d][4];
        }
    }

    function carregar(tipo) {
        const s = document.getElementById('status-vip');
        const m = document.getElementById('status-msg');
        const b = document.getElementById('b');
        s.style.display = 'block'; b.style.width = '0%';
        m.innerText = 'EXECUTANDO SCRIPTS...';
        setTimeout(() => { b.style.width = '100%'; m.innerText = '✅ CONCLUÍDO!'; }, 100);
    }
</script>

</body>
</html>
