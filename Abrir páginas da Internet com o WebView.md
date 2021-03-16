# Abrir páginas da Internet com o WebView
* AndroidManifest.xml
//Liberar Internet
<uses-permission android:name="android.permission.INTERNET" />
//Err ClearText -> Colocar como atributo da Tag Aplication
android:usesCleartextTraffic="true"


Activity.xml

<WebView
    android:id="@+id/webview"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_alignParentStart="true"
    android:layout_alignParentTop="true"
    android:layout_marginTop="0dp" />

.java
public class Home extends AppCompatActivity {
    //Variável WebView
    private WebView webView ;
    
    //Activity Em que Vai abrir
    final Activity activityAtual = this ;

    //Quando Inciar Activity...
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);

        //WebView 
	webView = (WebView) findViewById(R.id.webview);
	webView.setWebChromeClient(new WebChromeClient());
	webView.setWebViewClient(new WebViewClient());
	webView.getSettings().setJavaScriptEnabled(true);
	webView.loadUrl("http://139.59.210.161/");

    }


    //Quando botão voltar for clicado
    @Override
    public void onBackPressed() {
        if (webView.canGoBack()) {
            webView.goBack();

        }else {
            super.onBackPressed();
        }
    }

}
//Para executar mudança ULR: webView.loadUrl(“URL”);
