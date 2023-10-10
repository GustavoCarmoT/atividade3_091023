# atividade3_091023

Atividade 3 HTML

<!DOCTYPE html>
<html>
<head>
    <title>Contador de Caracteres</title>
</head>
<body>
    <h1>Contador de Caracteres</h1>

    <form id="form">
        <label for="inputString">Insira uma string:</label>
        <input type="text" id="inputString" name="inputString">
        <input type="submit" value="Contar">
    </form>

    <table border="1">
        <tr>
            <th>Tipo de Caractere</th>
            <th>Quantidade</th>
        </tr>
        <tr>
            <td>Vogais</td>
            <td id="vowelCount">0</td>
        </tr>
        <tr>
            <td>Consoantes</td>
            <td id="consonantCount">0</td>
        </tr>
        <tr>
            <td>Dígitos</td>
            <td id="digitCount">0</td>
        </tr>
        <tr>
            <td>Outros</td>
            <td id="otherCount">0</td>
        </tr>
    </table>

    <script>
        document.getElementById('form').addEventListener('submit', function (e) {
            e.preventDefault();

            // Obtém o valor da string inserida pelo usuário
            const inputString = document.getElementById('inputString').value;

            // Chama a função para contar os caracteres
            contarCaracteres(inputString);
        });

        function contarCaracteres(inputString) {
            const vowelCount = inputString.match(/[aeiouAEIOU]/g);
            const consonantCount = inputString.match(/[bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ]/g);
            const digitCount = inputString.match(/\d/g);
            const otherCount = inputString.match(/[^aeiouAEIOUbcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ\d]/g);

            // Atualiza as células da tabela com as contagens
            document.getElementById('vowelCount').textContent = vowelCount ? vowelCount.length : 0;
            document.getElementById('consonantCount').textContent = consonantCount ? consonantCount.length : 0;
            document.getElementById('digitCount').textContent = digitCount ? digitCount.length : 0;
            document.getElementById('otherCount').textContent = otherCount ? otherCount.length : 0;
        }
    </script>
</body>
</html>
