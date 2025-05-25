# tp-8-8-
calculatrice  realise en utilise le php
calculatrice  realise en utilise le php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Calculatrice PHP</title>
</head>
<body>
    <h2>Calculatrice en PHP</h2>
    <form action="calcul.php" method="post">
        <label for="nombre1">Nombre 1 :</label>
        <input type="number" step="any"  required><br><br>

        <label for="nombre2">Nombre 2 :</label>
        <input type="number" step="any"  required><br><br>

        <label for="operation">Opération :</label>
        <select name="operation">
            <option value="add">Addition (+)</option>
            <option value="sub">Soustraction (-)</option>
            <option value="mul">Multiplication (×)</option>
            <option value="div">Division (÷)</option>
        </select><br><br>

        <input type="submit" value="Calculer">
    </form>
</body>
</html>
calcul.php
?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $n1 = floatval($_POST["n1"]);
        $n2 = floatval($_POST["n2"]);
        $op = $_POST["op"];

        if ($op == '/' && $n2 == 0) {
            echo "<p style='color:red;'>Erreur : Division par zéro !</p>";
        } else {
            eval("\$res = $n1 $op $n2;");
            echo "<p>Résultat : $n1 $op $n2 = $res</p>";
        }
    }
    ?>
