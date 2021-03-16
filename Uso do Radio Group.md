# Uso do Radio Group (Múltipla Escolha)
## .Java
<pre><code>
    radioGroup = (RadioGroup) findViewById(R.id.opcoes) ;
    radioGroup.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() {
        @Override
        public void onCheckedChanged(RadioGroup group, int checkedId) {
            switch (checkedId ) {
                case R.id.btnUmAno:
                    aumentarUmAno () ;

                case R.id.btnSeisMeses:
                    aumentarSeisMeses();

                case R.id.btnDoisAnos:
                    aumentarDoisAnos();

            }
        }
    }) ;
</code></pre>
