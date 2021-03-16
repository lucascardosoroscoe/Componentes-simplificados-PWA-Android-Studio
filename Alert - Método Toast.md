# Método Toast para exibir uma mensagem ao usuário

## .java
<pre><code>
//chamar Alerta e passar a Mensagem
alert("Scan Cancelado");


//Método Para Mostrar Alerta na Tela
private void alert (String msg){
    Toast.makeText(getApplicationContext(), msg , Toast.LENGTH_LONG ).show();
}

</code></pre>