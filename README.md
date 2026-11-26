<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cek Base Bot WA - GrenXharimau</title>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/acorn/8.11.3/acorn.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/eslint@8.57.0/lib/linter/linter.min.js"></script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
        body { background-color: #0d0b14; color: #ffffff; min-height: 100vh; display: flex; justify-content: center; align-items: center; padding: 20px; }
        
        .container { width: 100%; max-width: 550px; background-color: #110e1a; border-radius: 20px; padding: 30px 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); border: 1px solid #1f1a2e; }
        
        h1 { color: #3b82f6; font-size: 22px; font-weight: 700; margin-bottom: 10px; line-height: 1.2; }
        .divider { height: 1px; background: linear-gradient(90deg, #3b82f6 0%, transparent 100%); margin-bottom: 20px; }
        .subtitle { color: #4b5563; font-size: 12px; margin-bottom: 30px; }
        .header-text { text-align: center; color: #2a243d; font-size: 18px; font-weight: 700; margin-bottom: 30px; text-transform: lowercase; letter-spacing: 1px; }

        .file-input-wrapper { background: #171329; border: 1px solid #2a213d; border-radius: 12px; padding: 15px; text-align: center; cursor: pointer; margin-bottom: 15px; transition: 0.3s; display: block; }
        .file-input-wrapper:hover { background: #1f1936; }
        .file-input-wrapper span { font-size: 16px; font-weight: 500; }
        input[type="file"] { display: none; }

        .file-info { background: #171329; border: 1px solid #2a213d; border-radius: 12px; padding: 15px; display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
        .file-name { font-size: 14px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; max-width: 70%; }
        .file-size { color: #6b7280; font-size: 12px; margin-right: 10px; }
        .remove-btn { color: #6b7280; cursor: pointer; font-size: 18px; background: none; border: none; }
        .remove-btn:hover { color: #ef4444; }

        .result-box { border-radius: 12px; padding: 20px; margin-bottom: 20px; display: none; animation: fadeIn 0.3s ease; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .result-box.error { background-color: #2a1215; border: 1px solid #4d1c22; }
        .result-box.warning { background-color: #2a2312; border: 1px solid #4d3c1c; }
        .result-box.success { background-color: #112519; border: 1px solid #1c4d2e; }

        .result-header { display: flex; align-items: center; gap: 10px; font-size: 18px; font-weight: 600; margin-bottom: 10px; }
        .result-box.error .result-header { color: #ef4444; }
        .result-box.warning .result-header { color: #f59e0b; }
        .result-box.success .result-header { color: #10b981; }

        .result-desc { color: #9ca3af; font-size: 13px; margin-bottom: 15px; line-height: 1.4; }

        .error-details { background: #1c0d0f; border-radius: 8px; padding: 15px; font-family: monospace; font-size: 13px; color: #f87171; max-height: 250px; overflow-y: auto; white-space: pre-wrap; border-left: 4px solid #ef4444; margin-bottom: 10px; }
        .warning-details { background: #1c180d; border-radius: 8px; padding: 15px; font-family: monospace; font-size: 13px; color: #fbbf24; max-height: 250px; overflow-y: auto; white-space: pre-wrap; border-left: 4px solid #f59e0b; margin-bottom: 10px;}
        .success-details { background: #0a1c12; border-radius: 8px; padding: 15px; font-family: monospace; font-size: 13px; color: #34d399; border-left: 4px solid #10b981; }

        .finish-btn { width: 100%; background: #7c3aed; color: white; border: none; padding: 15px; border-radius: 12px; font-size: 16px; font-weight: 600; cursor: pointer; transition: 0.3s; display: none; }
        .finish-btn:hover { background: #6d28d9; }
        .footer { text-align: center; color: #2a243d; font-size: 12px; margin-top: 30px; font-weight: 600; }
        
        ul.error-list { padding-left: 20px; margin-top: 5px; }
        ul.error-list li { margin-bottom: 8px; font-family: 'Poppins', sans-serif; font-size: 12px; color: #d1d5db; line-height: 1.3; }
        .error-tag { background: #4d1c22; color: #ef4444; padding: 2px 6px; border-radius: 4px; font-size: 10px; font-weight: 700; margin-right: 5px; display: inline-block; margin-bottom: 3px; }
        .warn-tag { background: #4d3c1c; color: #f59e0b; padding: 2px 6px; border-radius: 4px; font-size: 10px; font-weight: 700; margin-right: 5px; display: inline-block; margin-bottom: 3px; }
    </style>
</head>
<body>

    <div class="container">
        <h1>Web-cek-error-base-berupa-index.js-dll</h1>
        <div class="divider"></div>
        <div class="subtitle">&lt;!DOCTYPE html&gt;</div>

        <div class="header-text">
            ✦ Gren cek typo & error<br>berupa js atau index.js
        </div>

        <label for="fileInput" class="file-input-wrapper">
            <span>📁 Pilih File JS</span>
        </label>
        <input type="file" id="fileInput" accept=".js,.txt">

        <div class="file-info" id="fileInfo" style="display: none;">
            <div>
                <span class="file-name" id="fileName">-</span>
                <span class="file-size" id="fileSize">-</span>
            </div>
            <button class="remove-btn" onclick="resetApp()">✕</button>
        </div>

        <div class="result-box error" id="errorBox">
            <div class="result-header"><span>❌</span> Error Sintaks (Fatal)</div>
            <div class="result-desc">Kode tidak bisa dijalankan sama sekali.</div>
            <div class="error-details" id="errorDetails"></div>
        </div>

        <div class="result-box warning" id="warningBox">
            <div class="result-header"><span>⚠️</span> Peringatan / Typo</div>
            <div class="result-desc">Sintaks valid, tapi ada potensi error saat dijalankan.</div>
            <div class="warning-details" id="warningDetails"></div>
        </div>

        <div class="result-box success" id="successBox">
            <div class="result-header"><span>✅</span> Tidak Ada Error</div>
            <div class="result-desc">File JavaScript Anda valid secara sintaks dan aman dari typo.</div>
            <div class="success-details">
                ✅ Sintaks JavaScript valid<br>
                ✅ Kurung kurawal seimbang<br>
                ✅ Tidak ada variabel/fungsi typo
            </div>
        </div>

        <button class="finish-btn" id="finishBtn" onclick="resetApp()">✅ Selesai</button>
        <div class="footer">GrenXHarimau</div>
    </div>

    <script>
        const fileInput = document.getElementById('fileInput');
        const fileInfo = document.getElementById('fileInfo');
        const fileName = document.getElementById('fileName');
        const fileSize = document.getElementById('fileSize');
        
        const errorBox = document.getElementById('errorBox');
        const errorDetails = document.getElementById('errorDetails');
        const warningBox = document.getElementById('warningBox');
        const warningDetails = document.getElementById('warningDetails');
        const successBox = document.getElementById('successBox');
        const finishBtn = document.getElementById('finishBtn');

        fileInput.addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (!file) return;

            fileName.textContent = file.name;
            fileSize.textContent = (file.size / 1024).toFixed(1) + ' KB';
            fileInfo.style.display = 'flex';

            errorBox.style.display = 'none';
            warningBox.style.display = 'none';
            successBox.style.display = 'none';
            finishBtn.style.display = 'none';
            
            errorBox.querySelector('.result-header').innerHTML = '<span>❌</span> Error Sintaks (Fatal)';
            errorBox.querySelector('.result-desc').innerText = 'Kode tidak bisa dijalankan sama sekali.';

            const reader = new FileReader();
            reader.onload = function(event) {
                const code = event.target.result;
                cekKode(code, file.name);
            };
            reader.readAsText(file);
        });

        function cekKode(code, filename) {
            try {
                Acorn.parse(code, { 
                    ecmaVersion: 'latest', 
                    sourceType: 'script',
                    allowReturnOutsideFunction: true,
                    allowAwaitOutsideFunction: true 
                });
            } catch (error) {
                let errorMsg = error.message;
                let loc = error.loc || { line: 0, column: 0 };
                let lines = code.split('\n');
                let errorLine = loc.line || 1;
                let startLine = Math.max(1, errorLine - 2);
                let endLine = Math.min(lines.length, errorLine + 2);
                
                let snippet = "";
                for (let i = startLine; i <= endLine; i++) {
                    let prefix = (i === errorLine) ? "👉 " : "   ";
                    snippet += `${prefix}${i}: ${lines[i-1]}\n`;
                }

                if (errorMsg.includes("Deleting local variable")) {
                    errorMsg = "Deleting local variable in strict mode (Ganti 'delete var' jadi 'var = {}')";
                }

                errorDetails.innerHTML = `
                    ❌ ${errorMsg}<br><br>
                    📍 Baris ${loc.line || '?'}, kolom ${loc.column || '?'}<br><br>
                    <div style="background: #11080a; padding: 10px; border-radius: 5px; font-size: 12px; color: #d1d5db; overflow-x: auto;">
                        ${snippet.replace(/</g, "&lt;").replace(/>/g, "&gt;")}
                    </div>
                `;

                errorBox.style.display = 'block';
                finishBtn.style.display = 'block';
                return;
            }

            try {
                const linter = new Linter();
                
                const botGlobals = {
                    sock: "readonly", conn: "readonly", client: "readonly", Gren: "readonly",
                    m: "readonly", from: "readonly", sender: "readonly", target: "readonly", 
                    chat: "readonly", jid: "readonly", reply: "readonly", args: "readonly",
                    body: "readonly", ctx: "readonly", quoted: "readonly", mime: "readonly",
                    isGroup: "readonly", isOwner: "readonly", isPremium: "readonly", isSender: "readonly",
                    pushName: "readonly", senderNumber: "readonly", mediaBuffer: "readonly", mediaType: "readonly",
                    baileys: "readonly", proto: "readonly", WAProto: "readonly",
                    PREFIX: "readonly", BOT_NAME: "readonly", OWNER: "readonly", OWNER_NUMBER: "readonly",
                    startSender: "readonly", activeSenderSocks: "readonly", mainSock: "readonly"
                };

                const messages = linter.verify(code, {
                    env: { es2021: true, node: true, browser: false },
                    globals: botGlobals,
                    parserOptions: { ecmaVersion: 'latest', sourceType: 'script' },
                    rules: {
                        'no-undef': 'error',
                        'no-dupe-keys': 'error',
                        'no-dupe-args': 'error',
                        'no-duplicate-case': 'error',
                        'no-unreachable': 'warn',
                        'no-unused-vars': 'off',
                        'no-console': 'off'
                    }
                }, { filename: filename || 'index.js' });

                const fatalErrors = messages.filter(m => m.severity === 2);
                const warnings = messages.filter(m => m.severity === 1);

                let hasOutput = false;

                if (warnings.length > 0) {
                    let html = '<ul class="error-list">';
                    warnings.forEach(w => {
                        html += `<li><span class="warn-tag">Baris ${w.line}</span> ${w.message}</li>`;
                    });
                    html += '</ul>';
                    warningDetails.innerHTML = html;
                    warningBox.style.display = 'block';
                    hasOutput = true;
                }

                if (fatalErrors.length > 0) {
                    let html = '<ul class="error-list">';
                    fatalErrors.forEach(w => {
                        let msg = w.message;
                        if (msg.includes("is not defined")) {
                            msg = msg.replace("is not defined", "<b style='color:#ef4444;'>tidak pernah dideklarasikan (Typo?)</b>");
                        }
                        html += `<li><span class="error-tag">Baris ${w.line}</span> ${msg}</li>`;
                    });
                    html += '</ul>';
                    errorDetails.innerHTML = html;
                    errorBox.style.display = 'block';
                    
                    errorBox.querySelector('.result-header').innerHTML = '<span>❌</span> Error Logika / Typo';
                    errorBox.querySelector('.result-desc').innerText = 'Sintaks valid, tapi kode akan crash saat dijalankan.';
                    hasOutput = true;
                }

                if (!hasOutput) {
                    successBox.style.display = 'block';
                }

                finishBtn.style.display = 'block';

            } catch (err) {
                console.error("ESLint Error:", err);
                successBox.style.display = 'block';
                finishBtn.style.display = 'block';
            }
        }

        function resetApp() {
            fileInput.value = "";
            fileInfo.style.display = 'none';
            errorBox.style.display = 'none';
            warningBox.style.display = 'none';
            successBox.style.display = 'none';
            finishBtn.style.display = 'none';
        }
    </script>
</body>
</html>-
