# 6
```
public void button(View view)
    {
        TextView nameView = (TextView) findViewById(R.id.saveTextView);
        nameView.setText(name);
    }

    public void button2(View view)
    {
        TextView nameBox = (TextView)
                findViewById(R.id.editTextTextMultiLine);
        name = nameBox.getText().toString();
    }

    String name ="неопределено";
    final static String nameVariableKey = "NAME_VAR";
    final static String textViewTexKey = "TEXT_VIEW";

    @Override
    protected void onSaveInstanceState(Bundle outState)
    {
        outState.putString(nameVariableKey, name);
        TextView nameView = (TextView) findViewById(R.id.saveTextView);
        outState.putString(textViewTexKey, nameView.getText().toString());
        super.onSaveInstanceState(outState);
    }
    @Override
    protected void onRestoreInstanceState(Bundle savedInstanceState)
    {
        super.onRestoreInstanceState(savedInstanceState);
        name = savedInstanceState.getString(nameVariableKey);
        String textViewText= savedInstanceState.getString(textViewTexKey);
        TextView nameView = (TextView) findViewById(R.id.saveTextView);
        nameView.setText(textViewText);
    }
```
![image](https://user-images.githubusercontent.com/91714397/146625715-0f85108e-958e-4e79-a9ba-1305ff40e73a.png)
![image](https://user-images.githubusercontent.com/91714397/146625718-c182dd18-6c62-48c2-b4bc-44c15bee7b85.png)
