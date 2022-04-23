<?php
$meuValor = 0;
$meuNome = "Marilia Galdino";
$minhaIdade = 2022-1992;
echo "Meu nome é:".$meuNome; echo"</br>";
echo "Minha idade é:".$minhaIdade; echo"</br>";
echo date("d/m/y"); echo "</br>";
function remove_espacos($frase){
    return str_replace(" ", "", $frase);
}
$texto = "Eu programo em PHP"; echo"</br>";
echo remove_espacos($texto); echo"</br>";
$cpf = "000.000.000-00";
echo str_replace(array(".","-"),"",$cpf);echo "</br>";
echo strtolower("MARILIA"); echo "</br>";
echo strtoupper("marilia"); echo "</br>";
echo file_get_contents("aquivo.txt"); echo "</br>";
