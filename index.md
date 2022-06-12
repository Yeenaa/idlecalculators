<?php

function get_c($eingabe)
{
    $a = $eingabe * 21;
    $b = $eingabe * 85;
    $c = $eingabe * $a + $b * 585;

    return $c;
}

$c = null;
if (isset($_POST['eingabe'])) {
    $c = get_c($_POST['eingabe']);
}

?><!DOCTYPE html>

<html lang="en">

    <head>
        <meta charset="utf-8" />
        <title>Rechner</title>
    </head>

    <body>
    <form method="post" action="">
        <p><input type="text" name="eingabe" />
        <input type="submit" value="Berechnen" /></p>
    </form>

    <?php if ($c !== null) : ?>
        <div id="ergebnis"><?php echo $c; ?></div>
    <?php endif; ?>
        
    </body>

</html>
