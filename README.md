<img width="1919" height="993" alt="image" src="https://github.com/user-attachments/assets/473466a7-e52c-48de-86d7-b9d69b9105ae" />
код MainActivity.kt package com.example.layoutmastery

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val resultText = findViewById<TextView>(R.id.resultText)

        val btnOne = findViewById<Button>(R.id.btnOne)
        val btnTwo = findViewById<Button>(R.id.btnTwo)
        val btnThree = findViewById<Button>(R.id.btnThree)

        val searchInput = findViewById<EditText>(R.id.searchInput)
        val searchButton = findViewById<Button>(R.id.searchButton)
        val resetButton = findViewById<Button>(R.id.resetButton)

        btnOne.setOnClickListener {
            resultText.text = "Нажата кнопка 1. Вес элемента: 1."
        }

        btnTwo.setOnClickListener {
            resultText.text = "Нажата кнопка 2. Вес элемента: 1."
        }

        btnThree.setOnClickListener {
            resultText.text = "Нажата кнопка 3. Вес элемента: 1."
        }

        searchButton.setOnClickListener {
            val query = searchInput.text.toString().trim()

            if (query.isEmpty()) {
                resultText.text = "Сначала введи текст для поиска."
            } else {
                resultText.text = "Твой запрос: $query"
            }
        }

        resetButton.setOnClickListener {
            resultText.text = "Результат действий появится здесь."
            searchInput.text.clear()
        }
    }
}

Код Activity_main.xml <?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fillViewport="true"
    android:background="#F3F5F9">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Layout Mastery"
            android:textSize="28sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:gravity="center"
            android:padding="12dp" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Учебная лаборатория компоновки Android"
            android:textSize="15sp"
            android:textColor="#64748B"
            android:gravity="center"
            android:paddingBottom="20dp" />

        <!-- 1. LinearLayout: равномерное распределение -->
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="1. LinearLayout — веса"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:padding="8dp" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:weightSum="3"
            android:gravity="center"
            android:padding="8dp">

            <Button
                android:id="@+id/btnOne"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="1" />

            <Button
                android:id="@+id/btnTwo"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="2" /><Button
                android:id="@+id/btnThree"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="3" />
        </LinearLayout>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Три кнопки делят ширину строки поровну."
            android:textColor="#475569"
            android:padding="8dp" />

        <!-- 2. LinearLayout: поле поиска -->
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="2. Поле поиска"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:padding="8dp" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:gravity="center_vertical">

            <EditText
                android:id="@+id/searchInput"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:hint="Введите запрос"
                android:inputType="text"
                android:singleLine="true" />

            <Button
                android:id="@+id/searchButton"
                android:layout_width="48dp"
                android:layout_height="wrap_content"
                android:minWidth="0dp"
                android:padding="0dp"
                android:text="⌕"
                android:contentDescription="Найти" />

</LinearLayout>

        <!-- 3. FrameLayout: наложение -->
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="3. FrameLayout — слои"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:padding="8dp" />

        <FrameLayout
            android:layout_width="match_parent"
            android:layout_height="150dp"
            android:background="#DBEAFE">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:gravity="center"
                android:text="Фоновый слой"
                android:textColor="#1E40AF"
                android:textSize="20sp" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="bottom|end"
                android:layout_margin="12dp"
                android:background="#1D4ED8"
                android:padding="10dp"
                android:text="Слой поверх"
                android:textColor="#FFFFFF" />
        </FrameLayout>

        <!-- 4. RelativeLayout: относительное положение -->
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="4. RelativeLayout"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:padding="8dp" />

        <RelativeLayout
            android:layout_width="match_parent"
            android:layout_height="120dp"
            android:background="#DCFCE7"
            android:padding="12dp">

            <TextView
                android:id="@+id/relativeTitle"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:text="Центральный элемент"
                android:textColor="#166534"
                android:textSize="18sp" />

            <TextView
                android:layout_width="wrap_content"android:layout_height="wrap_content"
                android:layout_gravity="end"
                android:text="Текст справа"
                android:paddingTop="8dp" />
        </LinearLayout>

        <!-- 8. Разделитель между полями -->
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="8. Форма с разделителем"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#172554"
            android:padding="8dp" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:background="#FFFFFF"
            android:padding="12dp">

            <EditText
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Логин"
                android:inputType="text" />

            <View
                android:layout_width="match_parent"
                android:layout_height="1dp"
                android:background="#E0E0E0" />

            <EditText
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Пароль"
                android:inputType="textPassword" />
        </LinearLayout>

        <TextView
            android:id="@+id/resultText"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Результат действий появится здесь."
            android:textColor="#334155"
            android:padding="12dp" />

        <Button
            android:id="@+id/resetButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Сбросить результат" />

</LinearLayout>
</ScrollView>

<img width="1919" height="1033" alt="image" src="https://github.com/user-attachments/assets/39e0536e-88c6-40a1-b650-8744b8d27ca2" />
<FrameLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:background="#F1F5F9"
    android:padding="12dp">

    <!-- Задание 1. Аватар с индикатором онлайн -->
    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="88dp">

        <ImageView
            android:id="@+id/avatarImage"
            android:layout_width="64dp"
            android:layout_height="64dp"
            android:layout_gravity="start|center_vertical"
            android:src="@android:drawable/sym_def_app_icon"
            android:background="#DBEAFE"
            android:contentDescription="Аватар пользователя" />

        <View
            android:id="@+id/onlineIndicator"
            android:layout_width="18dp"
            android:layout_height="18dp"
            android:layout_gravity="start|bottom"
            android:layout_marginStart="48dp"
            android:layout_marginBottom="8dp"
            android:background="@drawable/online_circle" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_vertical"
            android:layout_marginStart="80dp"
            android:text="Пользователь онлайн"
            android:textColor="#172554"
            android:textSize="16sp" />

    </FrameLayout>

    <!-- Задание 2. Кнопка и индикатор загрузки -->
    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="64dp"
        android:layout_marginTop="88dp">

        <Button
            android:id="@+id/submitButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Подтвердить отправку" />

        <ProgressBar
            android:id="@+id/submitProgress"
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_gravity="center"
            android:visibility="gone" />

    </FrameLayout>

    <!-- Задание 3. Плавающая кнопка -->
    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="180dp"
        android:layout_marginTop="164dp"
        android:background="#FFFFFF">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:padding="16dp"
            android:text="Заметки&#10;&#10;FrameLayout позволяет располагать элементы слоями друг над другом."
            android:textColor="#334155"
            android:textSize="16sp" />

        <Button
            android:id="@+id/fabButton"
            android:layout_width="56dp"
            android:layout_height="56dp"
            android:layout_gravity="bottom|end"
            android:layout_margin="24dp"
            android:minWidth="0dp"
            android:text="+"
            android:textSize="26sp" />

    </FrameLayout>

    <!-- Задание 4. Контейнер для фрагмента -->
    <FrameLayout
        android:id="@+id/fragmentContainerView"
        android:layout_width="match_parent"
        android:layout_height="120dp"
        android:layout_marginTop="344dp"
        android:background="#E2E8F0">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:text="Область для фрагмента"
            android:textColor="#475569" />

    </FrameLayout>

    <!-- Задание 5. Видео-превью с Play -->
    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="160dp"
        android:layout_marginTop="464dp"
        android:background="#0F172A">

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:src="@android:drawable/ic_media_play"
            android:scaleType="center"
android:contentDescription="Воспроизведение видео"
            android:tint="#FFFFFF" />

        <TextView

android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="bottom|start"
            android:layout_margin="12dp"
            android:text="Видео-превью"
            android:textColor="#FFFFFF"
            android:textSize="16sp" />

    </FrameLayout>

</FrameLayout>


<!-- 4
. RelativeLayout: относительное позиционирование --><TextV
iew    an
droid:layout_width="match_parent"    an
droid:layout_height="wrap_content"    an
droid:text="4. RelativeLayout — карточка товара"    an
droid:textSize="20sp"    an
droid:textStyle="bold"    an
droid:textColor="#172554"    an
droid:padding="8dp" /><Relat

iveLayout    an
droid:layout_width="match_parent"    an
droid:layout_height="140dp"    an
droid:layout_margin="8dp"    an
droid:padding="12dp"    an
droid:background="#E0F2FE">    <!

-- Изображение товара -->    <T
extView      
  android:id="@+id/productImage"      
  android:layout_width="90dp"      
  android:layout_height="match_parent"      
  android:gravity="center"      
  android:text="🎧"      
  android:textSize="42sp"      
  android:background="#BAE6FD" />    <!

-- Название справа от изображения -->    <T
extView      
  android:id="@+id/productName"      
  android:layout_width="match_parent"      
  android:layout_height="wrap_content"      
  android:layout_toEndOf="@id/productImage"      
  android:layout_marginStart="12dp"      
  android:text="Беспроводные наушники"      
  android:textSize="16sp"      
  android:textStyle="bold"      
  android:textColor="#172554" />    <!

-- Цена под названием и у нижнего края изображения -->    <T
extView      
  android:id="@+id/productPrice"      
  android:layout_width="wrap_content"      
  android:layout_height="wrap_content"      
  android:layout_toEndOf="@id/productImage"      
  android:layout_alignParentBottom="true"      
  android:layout_marginStart="12dp"      
  android:text="2 490 ₽"      
  android:textSize="20sp"      
  android:textStyle="bold"      
  android:textColor="#047857" /></Rela

tiveLayout>


<andro
idx.constraintlayout.widget.ConstraintLayout    xm
lns:android="http://schemas.android.com/apk/res/android"    xm
lns:app="http://schemas.android.com/apk/res-auto"    an
droid:layout_width="match_parent"    an
droid:layout_height="wrap_content"    an
droid:padding="8dp"    an
droid:background="#F3E8FF">    <T

extView      
  android:id="@+id/bannerText"      
  android:layout_width="0dp"      
  android:layout_height="0dp"      
  android:gravity="center"      
  android:text="Баннер 16:9"      
  android:textSize="22sp"      
  android:textStyle="bold"      
  android:textColor="#6B21A8"      
  android:background="#E9D5FF"      
  app:layout_constraintDimensionRatio="16:9"      
  app:layout_constraintStart_toStartOf="parent"      
  app:layout_constraintEnd_toEndOf="parent"      
  app:layout_constraintTop_toTopOf="parent"      
  app:layout_constraintBottom_toBottomOf="parent" /></andr

oidx.constraintlayout.widget.ConstraintLayout>

<img width="1902" height="1021" alt="image" src="https://github.com/user-attachments/assets/66c07f6c-7b01-438c-a595-b30384278f6d" />
<!-- 5. HorizontalScrollView: лента историй -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="6. Лента историй"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<HorizontalScrollView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:scrollbars="none"
    android:fillViewport="false"
    android:padding="8dp">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <LinearLayout
            android:layout_width="76dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:gravity="center"
            android:layout_marginEnd="12dp">

            <TextView
                android:layout_width="64dp"
                android:layout_height="64dp"
                android:gravity="center"
                android:text="🙂"
                android:textSize="32sp"
                android:background="@drawable/online_circle" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Аня"
                android:textSize="12sp"
                android:paddingTop="4dp" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="76dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:gravity="center"
            android:layout_marginEnd="12dp">

            <TextView
                android:layout_width="64dp"
                android:layout_height="64dp"
                android:gravity="center"
                android:text="😎"
                android:textSize="32sp"
                android:background="@drawable/online_circle" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Макс"
                android:textSize="12sp"
                android:paddingTop="4dp" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="76dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:gravity="center"
            android:layout_marginEnd="12dp">

            <TextView
                android:layout_width="64dp"
                android:layout_height="64dp"
                android:gravity="center"
                android:text="🐱"
                android:textSize="32sp"
                android:background="@drawable/online_circle" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Мила"
                android:textSize="12sp"
                android:paddingTop="4dp" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="76dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:gravity="center"
            android:layout_marginEnd="12dp">

            <TextView
                android:layout_width="64dp"
                android:layout_height="64dp"
                android:gravity="center"
                android:text="🎮"
                android:textSize="32sp"
                android:background="@drawable/online_circle" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Даня"
                android:textSize="12sp"
                android:paddingTop="4dp" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="76dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"android:gravity="center"
            android:layout_marginEnd="12dp">

            <TextView
                android:layout_width="64dp"
                android:layout_height="64dp"
                android:gravity="center"
                android:text="🐼"
                android:textSize="32sp"
                android:background="@drawable/online_circle" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Саша"
                android:textSize="12sp"
                android:paddingTop="4dp" />
        </LinearLayout>

    </LinearLayout>
</HorizontalScrollView>

<img width="1911" height="997" alt="image" src="https://github.com/user-attachments/assets/0171fb64-9dcd-46b0-93e9-91e079bf3985" />
Тема 6 
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 2. Упакованная цепочка"
    android:textStyle="bold"
    android:textSize="18sp"
    android:textColor="#172554"
    android:padding="8dp" />

<androidx.constraintlayout.widget.ConstraintLayout
    android:layout_width="match_parent"
    android:layout_height="180dp"
    android:background="#F3E8FF">

    <TextView
        android:id="@+id/tvChainTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Мой профиль"
        android:textSize="20sp"
        android:textStyle="bold"
        android:textColor="#6B21A8"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toTopOf="@id/tvChainSubtitle"
        app:layout_constraintVertical_chainStyle="packed"
        app:layout_constraintVertical_bias="0.2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

    <TextView
        android:id="@+id/tvChainSubtitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Настройте свой аккаунт"
        android:textColor="#7E22CE"
        app:layout_constraintTop_toBottomOf="@id/tvChainTitle"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

<img width="1900" height="965" alt="image" src="https://github.com/user-attachments/assets/1801ecc2-8ffa-4138-ac23-ba98488022af" />
Тема 7. Оптимизация верстки и борьба с Overdraw
Цель работы: изучить способы оптимизации XML-разметки Android-приложения и уменьшения избыточной перерисовки элементов интерфейса.
Ход работы:
Проверена структура XML-разметки приложения.
Изучено использование контейнеров LinearLayout, FrameLayout, RelativeLayout и ConstraintLayout.
Рассмотрена возможность уменьшения количества лишних фоновых слоёв.
Изучен механизм Overdraw и его влияние на производительность приложения.
Вывод: в ходе работы изучены основные способы оптимизации интерфейса Android. Уменьшение количества лишних фонов и избыточной вложенности контейнеров позволяет снизить нагрузку при отрисовке интерфейса.



