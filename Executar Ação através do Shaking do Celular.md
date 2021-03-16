# Executar ação através do Shaking do Celular
## .java

<pre><code>
    import android.hardware.Sensor;
    import android.hardware.SensorEvent;
    import android.hardware.SensorEventListener;
    import android.hardware.SensorManager;




    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);
        //Variáveis Do Sensor
        sm = (SensorManager) getSystemService(Context.SENSOR_SERVICE);
        sm.registerListener(sensorListener, sm.getDefaultSensor(Sensor.TYPE_ACCELEROMETER), SensorManager.SENSOR_DELAY_NORMAL);
        acelVal = SensorManager.GRAVITY_EARTH ;
        acelLast = SensorManager.GRAVITY_EARTH ;
        shake = 0.00f ;
        //Fim Das Variáveis Do Sensor
    }


    //Método Para Identificar o Shake
    private final SensorEventListener sensorListener = new SensorEventListener() {
        @Override
        public void onSensorChanged(SensorEvent sensorEvent) {
            float x = sensorEvent.values[0] ;
            float y = sensorEvent.values[1] ;
            float z = sensorEvent.values[2] ;


            acelLast = acelVal ;
            acelVal = (float) Math.sqrt((double) (x*x + y*y + z*z) ) ;
            float delta = acelVal - acelLast ;
            shake = shake * 0.9f + delta ;


            if (shake > 12) {
                //Ação Para Executar Quando o Shake Acontece
                    }
        }

        @Override
        public void onAccuracyChanged(Sensor sensor, int accuracy) {

        }
    };
</code></pre>
