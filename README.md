# practice_graphic
Работа с графическими элементами
![image](https://user-images.githubusercontent.com/92590831/144443556-0741ac70-9057-4256-acd2-7aac21e62a99.png)

Контрольные вопросы
1. Что такое событийно-ориентированное программирование?
2. Какие события вы использовали в своем приложении?
3. С помощью какого класса предоставляется доступ к ресурсам из
кода Java?
4. Какие основные квалификаторы ресурсов вы знаете?
5. Какие основные XML-атрибуты используются для задания
расположения виджета на экране?
6. Какие основные XML-атрибуты используются для задания
отображения виджета на экране?
7. Какие существуют соглашения в порядке наименования действий?
8. Как передать информацию в активность используя неявный вызов?
9. Какие еще параметры можно задавать при создании неявного
интента?
10. Зачем нужна категория в интент-фильтрах? Какие существуют
категории?
11. Зачем нужен элемент &lt;requestFocus&gt;?
12. Зачем нужны аргументы requestCode и resultCode в обратном
интенте?
13. Зачем делить приложение на несколько окно? Почему нельзя
использовать разные расположения?
14. Что такое интент и зачем он нужен?
15. Как вызвать определенное окно своего приложение? А
другого?
16. Что такое таск? Почему при перемещении между окнами
работает кнопка “Назад”?

Дополнительные задания
1. Создайте приложение, на главном окне которого будет расположено
поле ввода текста и при нажатии на кнопку “перейти” будет
запускаться браузер по введенному пользователем адресу.
2. Создайте приложение, отвечающее на какое-либо стандартное
системное действие. Проверьте его работоспособность.
3. Создайте приложение, которое выводит текстовую надпись и
предлагает выбрать цвет и выравнивание надписи. Выбор должен
производиться в двух разных активностях. При возврате в основную
активность форматирование надписи должно меняться.
4. (*) Создайте приложение, запускающее приложение камеры. Когда
пользователь делает снимок, он должен вернуться в наше
приложение, и оно должно отобразить его в виде миниатюры на
экране.



<AbsoluteLayout
        android:layout_width="409dp"
        android:layout_height="210dp"
        android:orientation="horizontal"
        tools:layout_editor_absoluteX="1dp"
        tools:layout_editor_absoluteY="1dp">

        <EditText
            android:id="@+id/txt_site"
            android:layout_width="240dp"
            android:layout_height="45dp"
            android:layout_x="74dp"
            android:layout_y="44dp"
            android:text="https://github.com/CodeG3ass/Android_Studio_KR/blob/main/KontrolWork/app/src/main/java/com/example/myapplication/MainActivity.java" />

        <Button
            android:id="@+id/button_open"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_x="118dp"
            android:layout_y="126dp"
            android:text="Button" />
    </AbsoluteLayout>


public class MainActivity extends AppCompatActivity {

    EditText txt_site;
    Button Sbutton;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        txt_site = (EditText) findViewById(R.id.txt_site);
        Sbutton = (Button) findViewById(R.id.button_open);
        Sbutton.setOnClickListener(this::OnClick);
    }


    public void OnClick(View v){
        Intent browserIntent = new Intent(Intent.ACTION_VIEW, Uri.parse(txt_site.getText().toString()));
        startActivity(browserIntent);

    }
}
