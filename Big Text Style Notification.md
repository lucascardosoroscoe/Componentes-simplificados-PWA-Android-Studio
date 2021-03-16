# Big Text Style Notification
## .java

<pre><code>
    Button btNotificar;
    TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);

        btNotificar = (Button) findViewById(R.id.btnNotificacao);
        textView = (TextView) findViewById(R.id.textView);

        btNotificar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                textView.setText("Você Clicou no Botão");
                BigTextStyleNotification() ;
            }
        });
    }






    private void BigTextStyleNotification() {
        int notificationId = 1;
        NotificationCompat.Builder builder = new NotificationCompat.Builder(this) ;
        builder.setSmallIcon(R.drawable.ic_launcher_foreground)
                .setLargeIcon(BitmapFactory.decodeResource(getResources(), R.drawable.ic_launcher_foreground))
                .setContentTitle("Lucas Roscoe")
                .setStyle(new NotificationCompat.BigTextStyle().bigText(getResources().getString(R.string.mensagem)))
                .setAutoCancel(true);

        Uri path = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION) ;
        builder.setSound(path);

        NotificationManager notificationManager = (NotificationManager) getSystemService(NOTIFICATION_SERVICE);
        notificationManager.notify(notificationId, builder.build()) ;

    }
    
</code></pre>
