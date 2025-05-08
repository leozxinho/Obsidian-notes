
extensão vscode: <font color="#f79646">PHP IntelliSense</font>


Sintaxe básica PHP:

	Tipos de dados: ['string','int','float','bool','array','objetct','null']

	     $nome = "Leonardo"; // string
	     $idade = 25; // int
	     $altura = 1.78; // float
	     $hetero = true; // bool
	     $lista = [1, 2, 3] // array

       Tipos de Operadores: + - * / % // Soma, subtração, multiplicação, divisão, módulo
       Atribuição -> = += -= *= /= %= 
       Comparação -> == === != !== > < >= <=
        == compara valor
        === compara valor e tipo
       Lógicos -> && (e)  || (ou) ! (não)




Estruturas de controle:

    if = Executa um bloco de código se uma condição for verdadeira
    else = Pode ser usado para tratar o contrário
    elseif = Para chegar outras condições

    Exemplo de código:

     $idade = 20;

    if ($idade >= 18) {
        echo "Maior de idade";
    } elseif ($idade >= 12) {
        echo "Adolescente";
    } else {
        echo "Criança";
    }


    switch = É útil quando você precisa comparar uma mesma variável com vários valores diferentes.
    
    Exemplo de código:

     $dia = "terça";

    switch ($dia) {
    case "segunda":
        echo "Início da semana";
        break;
    case "terça":
        echo "Dia de produtividade";
        break;
    case "sexta":
        echo "Quase fim de semana";
        break;
    default:
        echo "Dia comum";
    }



Laços de Repetição (Loops):

<font color="#00b0f0">while</font>
    
     $i = 1;
    while ($i <= 5) {
        echo $i;
        $i++;
    }


<font color="#00b0f0">do...while</font>

    $i = 1;
    do {
        echo $i;
        $i++;
    } while ($i <= 5);


<font color="#00b0f0">for</font>

    for ($i = 1; $i <= 5; $i++) {
        echo $i;
    }

<font color="#00b0f0">foreach (para arrays)</font>

    $frutas = ["maçã", "banana", "laranja"];

    foreach ($frutas as $fruta) {
        echo $fruta;
    }


