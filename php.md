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

class Mamifero{
    public function __construct($nome, $idade, $sexo)
    {
        $this->nome=$nome;
        $this->idade=$idade;
        $this->sexo=$sexo;
    }
}
$cachorro=new Mamifero("Sansao", 12.9, "M");

print_r($cachorro);

//transformar php para javascript
$mamifero=["nome",=>"sansao", "idade"=>12, "peso"=>45];
echo json_encode($mamifero); echo"</br>;

//transformar de javascript para php
$mamifero1='{"nome":"sansao","idade":12, "peso":45}';

$array = json_decode($mamifero1);
print_r($array);


$idade = 35;
function maiorIdade($idade){
    if($idade>=18){
        echo "Sua idade é:".$idade. ".Você é maior de idade";
        echo "Sua idade é:".$idade. ".Você é menor de idade";
        }
}
