# Leitor de QR CODE
## build.gradle (Module: app) //Importação da biblioteca

<pre><code>
implementation 'com.google.zxing:core:3.2.1'
implementation 'com.journeyapps:zxing-android-embedded:3.2.0@aar'
</code></pre>

## .java

<pre><code>
//Comando Para Abrir Laitor de Qr Code
IntentIntegrator integrator = new IntentIntegrator(activityAtual);
integrator.setDesiredBarcodeFormats(IntentIntegrator.QR_CODE_TYPES);
integrator.setPrompt("Scaneie o QRCODE");
integrator.setCameraId(0);
integrator.initiateScan();
alert("Sucesso") ;
 
//Quando QRCode obter resultado
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    IntentResult result = IntentIntegrator.parseActivityResult(requestCode, resultCode, data);
    if (result != null){
        if (result.getContents() != null){
               //O que fazer com o valor obtido no QR CODE
		webView.loadUrl(result.getContents());
        }else{
               //O que fazer caso o QR CODE não obtenha resultado
        }
    }else{
        Home.super.onActivityResult(requestCode, resultCode, data);
    }
}
</code></pre>
