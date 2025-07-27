<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu App de Sustentabilidade</title>
    <link rel="stylesheet" href="src/css/style.css">
    <link rel="stylesheet" href="src/css/components.css">
</head>
<body>
    <header>
        <h1>Ideias para um Planeta Melhor</h1>
    </header>

    <main id="app-container">
        <section class="ideas-list">
            <h2>Dicas de Reciclagem</h2>
            <div id="recycling-ideas-cards">
                </div>
        </section>

        <section class="ecosystem-tips">
            <h2>Salvando Nosso Ecossistema</h2>
            <div id="ecosystem-tips-cards">
                </div>
        </section>

        <div class="icon-section">
            <svg width="50" height="50" viewBox="0 0 100 100">
                <use href="assets/icons/circle-icon.svg#S--circle" class="app-icon green-icon"></use>
            </svg>
            <p>Seu impacto ambiental:</p>
            <div id="impact-indicator"></div>
        </div>
    </main>

    <footer>
        <p>&copy; 2025 - App Sustentabilidade</p>
    </footer>

    <script src="src/js/app.js"></script>
    <script src="src/js/ui.js"></script>
    <script src="src/js/data.js"></script>
</body>
</html>
