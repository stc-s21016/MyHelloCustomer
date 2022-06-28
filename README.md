#アプリプログラミングⅠ

##　第10週　提出課題
S21-016　草野　友哉

###1-1.問題
「住まい」と「お名前」の入力欄を持ち、表示ボタンを押すと「＊＊＊にお住いの＃＃＃さん、こんにちは！」と表示するアプリを作成しなさい。
加えて、「住まいクリア」ボタンと「お名前クリア」ボタンも追加して、それぞれをクリックすると「住まい」と「お名前」をそれぞれクリアできるようにしなさい。
レイアウトは自由に設定できるものとします。プロジェクト名はMyHelloCustomerとします。


###2-1.ソースコード
```java
package com.example.myhellocustomer1;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;


public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btClick = findViewById(R.id.btClick);

        HelloListener listener = new HelloListener();

        btClick.setOnClickListener(listener);

        Button btclear = findViewById(R.id.btclear);
        Button btclear1 = findViewById(R.id.btclear1);

        btclear.setOnClickListener(listener);
        btclear1.setOnClickListener(listener);
    }
    //リスナ・クラス　<=　イベントの監視
    private class HelloListener implements View.OnClickListener {
        //イベントハンドラ　<=　イベント発生時の処理
        @Override
        public void onClick(View view) {
            EditText input = findViewById(R.id.etName);
            EditText input1 = findViewById(R.id.ethome);
            TextView output = findViewById(R.id.tvOutput);

            int id = view.getId();

            switch (id) {
                case R.id.btClick:
                    String inputStr = input.getText().toString();
                    String inputStr1 = input1.getText().toString();
                    output.setText(inputStr1+"にお住いの"+inputStr + "さん、こんにちは!");
                    break;
                case R.id.btclear:

                    input.setText("");

                    output.setText("");
                    break;
                case R.id.btclear1:

                    input1.setText("");

                    output.setText("");
                    break;
            }
        }
    }
}
```
###3.説明
クリアボタンとその機能を複製し、それぞれの変数名を付け実行した。
###4.感想
GitHubの使い方がわかりません。
