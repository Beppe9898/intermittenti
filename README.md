# intermittenti<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Comunicazione Intermittenti</title>

    <!-- PWA setup -->
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#3498db">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="ComInt">

    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 15px;
            background-color: #f0f2f5;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .intro {
            background: #e8f4ff;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 25px;
            border-left: 4px solid #3498db;
        }

        h1 {
            color: #2c3e50;
            font-size: 24px;
            margin: 0 0 15px 0;
        }

        .istruzioni {
            font-size: 16px;
            line-height: 1.5;
        }

        .istruzioni ul, .istruzioni ol {
            margin: 10px 0;
            padding-left: 25px;
        }

        .istruzioni li {
            margin: 5px 0;
        }

        .nota {
            background: #fff3cd;
            padding: 10px;
            border-radius: 4px;
            margin-top: 15px;
            font-size: 14px;
            color: #856404;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #2c3e50;
        }

        input[type="text"],
        input[type="email"],
        input[type="date"] {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        button {
            background-color: #3498db;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            font-size: 16px;
        }

        button:hover {
            background-color: #2980b9;
        }

        .check-item {
            color: #28a745;
        }

        .step-item {
            color: #3498db;
        }

        #xmlOutput {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 4px;
            margin-top: 20px;
            font-family: monospace;
            overflow-x: auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Introduzione -->
        <div class="intro">
            <h1>Comunicazione Intermittenti</h1>
            
            <div class="istruzioni">
                <p><strong>Gentile Datore di Lavoro,</strong></p>
                <p>Questa app permette di:</p>
                <ul>
                    <li class="check-item">✓ Generare la comunicazione intermittenti</li>
                    <li class="check-item">✓ Scaricare il file XML</li>
                    <li class="check-item">✓ Inviare direttamente via email</li>
                </ul>

                <p><strong>Come utilizzarla:</strong></p>
                <ol>
                    <li class="step-item">Inserisci i tuoi dati</li>
                    <li class="step-item">Aggiungi i dati dei lavoratori</li>
                    <li class="step-item">Clicca "Genera XML"</li>
                </ol>

                <div class="nota">
                    <strong>Nota:</strong> I campi con asterisco (*) sono obbligatori
                </div>
            </div>
        </div>

        <!-- Form -->
        <form id="comunicazioneForm">
            <div class="form-group">
                <label for="codiceFiscaleDatore">Codice Fiscale Datore *</label>
                <input type="text" id="codiceFiscaleDatore" required>
            </div>

            <div class="form-group">
                <label for="emailDatore">Email Datore *</label>
                <input type="email" id="emailDatore" required>
            </div>

            <div class="form-group">
                <label>
                    <input type="checkbox" id="annullamento">
                    Annullamento
                </label>
            </div>

            <div id="lavoratori">
                <div class="lavoratore">
                    <h3>Lavoratore</h3>
                    <div class="form-group">
                        <label>Codice Fiscale Lavoratore *</label>
                        <input type="text" class="codiceFiscaleLavoratore" required>
                    </div>

                    <div class="form-group">
                        <label>Codice Comunicazione</label>
                        <input type="text" class="codiceComunicazione">
                    </div>

                    <div class="form-group">
                        <label>Data Inizio *</label>
                        <input type="date" class="dataInizio" required>
                    </div>

                    <div class="form-group">
                        <label>Data Fine</label>
                        <input type="date" class="dataFine">
                    </div>
                </div>
            </div>

            <button type="button" id="aggiungiLavoratore">Aggiungi Lavoratore</button>
            <button type="button" id="generaXML">Genera XML</button>
        </form>

        <div id="xmlOutput"></div>
    </div>

    <script>
        // Il codice JavaScript rimane lo stesso del precedente esempio
    </script>
</body>
</html>
