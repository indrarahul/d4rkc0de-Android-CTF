# Look</br>   20

> Look Closely
>
> [crackme.apk](./../crackme.apk)

After Installing and on starting we get this on the screen.

<img src="sc1.png" width="250">

Well they asked to look closely and so I did. 

<img src="sc2.png" width="250">

This gave me an idea to check the activity_main in the layout folder.

I used [jadx](https://github.com/skylot/jadx) for decompilation.

```public class MainActivity extends AppCompatActivity {
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView((int) R.layout.activity_main);
        setSupportActionBar((Toolbar) findViewById(R.id.toolbar));
        ((FloatingActionButton) findViewById(R.id.fab)).setOnClickListener(new OnClickListener() {
            public void onClick(View view) {
                Snackbar.make(view, (CharSequence) "Replace with your own action", 0).setAction((CharSequence) "Action", null).show();
            }
        });
    }

    public boolean onCreateOptionsMenu(Menu menu) {
        getMenuInflater().inflate(R.menu.menu_main, menu);
        return true;
    }

    public boolean onOptionsItemSelected(MenuItem item) {
        if (item.getItemId() == R.id.action_settings) {
            return true;
        }
        return super.onOptionsItemSelected(item);
    }
}```

