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



50 заданий
1 блок
<img width="298" height="563" alt="image" src="https://github.com/user-attachments/assets/99da372f-d3d2-4275-bde9-8408b58f1412" />
<!-- Задание 1. Карточка маркетплейса -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 1. Карточка маркетплейса"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="12dp"
    android:background="#FFFFFF">

    <FrameLayout
        android:id="@+id/productImageFrame"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:background="#E8EEFA"
        app:layout_constraintDimensionRatio="1:1"
        app:layout_constraintWidth_max="240dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent">

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:src="@android:drawable/ic_menu_gallery"
            android:scaleType="centerInside"
            android:contentDescription="Изображение товара" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="top|start"
            android:layout_margin="8dp"
            android:paddingHorizontal="10dp"
            android:paddingVertical="6dp"
            android:background="#E53935"
            android:text="-30%"
            android:textColor="#FFFFFF"
            android:textStyle="bold"
            android:textSize="14sp" />

    </FrameLayout>

    <TextView
        android:id="@+id/productTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="12dp"
        android:maxLines="2"
        android:ellipsize="end"
        android:text="Беспроводные наушники с зарядным кейсом"
        android:textColor="#172033"
        android:textSize="16sp"
        android:textStyle="bold"
        app:layout_constraintTop_toBottomOf="@id/productImageFrame"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

    <TextView
        android:id="@+id/oldPrice"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:text="4 990 ₽"
        android:textColor="#888888"
        android:textSize="14sp"
        android:paintFlags="16"
        app:layout_constraintTop_toBottomOf="@id/productTitle"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/newPrice"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="2dp"
        android:text="3 490 ₽"
        android:textColor="#D32F2F"
        android:textSize="24sp"
        android:textStyle="bold"
        app:layout_constraintTop_toBottomOf="@id/oldPrice"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintBottom_toBottomOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

<img width="403" height="599" alt="image" src="https://github.com/user-attachments/assets/c085833f-4adb-44c3-83cf-3cb48567ea1c" />
<!-- Задание 2. Карточка ресторана доставки -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 2. Карточка ресторана доставки"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="12dp"
    android:orientation="horizontal"
    android:gravity="center_vertical"
    android:background="#FFFFFF">

    <!-- Логотип ресторана -->
    <ImageView
        android:layout_width="76dp"
        android:layout_height="76dp"
        android:src="@android:drawable/ic_menu_gallery"
        android:background="#FFF0D9"
        android:scaleType="centerInside"
        android:contentDescription="Логотип ресторана" />

    <!-- Информация о ресторане -->
    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:layout_marginStart="12dp"
        android:orientation="vertical">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Burger House"
            android:textSize="17sp"
            android:textStyle="bold"
            android:textColor="#172033"
            android:maxLines="1" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="6dp"
            android:text="Доставка: 25–35 мин"
            android:textSize="14sp"
            android:textColor="#64748B" />

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="5dp"
            android:orientation="horizontal"
            android:gravity="center_vertical">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="★"
                android:textColor="#F59E0B"
                android:textSize="17sp" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginStart="4dp"
                android:text="4.8"
                android:textColor="#172033"
                android:textStyle="bold"
                android:textSize="14sp" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginStart="6dp"
                android:text="· Бургеры"
                android:textColor="#64748B"
                android:textSize="13sp" />
        </LinearLayout>
    </LinearLayout>

    <!-- Кнопка избранного -->
    <TextView
        android:layout_width="36dp"
        android:layout_height="36dp"
        android:gravity="center"
        android:text="♡"
        android:textColor="#E53935"
        android:textSize="28sp"
        android:contentDescription="Добавить в избранное" />

</LinearLayout>


задание 3 <LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_marginEnd="80dp"
    android:layout_gravity="start|center_vertical"
    android:orientation="vertical"
    android:gravity="center_vertical">

    
    <!-- Задание 4. Виртуальная банковская карта -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 4. Виртуальная банковская карта"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<androidx.constraintlayout.widget.ConstraintLayout
    android:layout_width="match_parent"
    android:layout_height="210dp"
    android:layout_margin="8dp"
    android:padding="20dp"
    android:background="@drawable/sale_gradient">

    <TextView
        android:id="@+id/bankName"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TRADLY BANK"
        android:textColor="#FFFFFF"
        android:textStyle="bold"
        android:textSize="18sp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/cardContactless"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=")))"
        android:textColor="#FFFFFF"
        android:textSize="24sp"
        android:rotation="90"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/cardNumber"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="••••  ••••  ••••  2048"
        android:textColor="#FFFFFF"
        android:textSize="20sp"
        android:letterSpacing="0.08"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintBottom_toTopOf="@id/cardOwner"
        android:layout_marginBottom="14dp" />

    <TextView
        android:id="@+id/cardOwner"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ALEX MORGAN"
        android:textColor="#FFFFFF"
        android:textSize="14sp"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintBottom_toBottomOf="parent" />

    <TextView
        android:id="@+id/cardExpiry"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="VALID THRU  08/29"
        android:textColor="#EDE9FE"
        android:textSize="11sp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintBottom_toBottomOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>


<!-- Задание 5. Карточка профиля пользователя -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 5. Карточка профиля пользователя"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="16dp"
    android:orientation="horizontal"
    android:gravity="center_vertical"
    android:background="#F1F5F9">

    <FrameLayout
        android:layout_width="72dp"
        android:layout_height="72dp">

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:src="@android:drawable/ic_menu_myplaces"
            android:background="#DBEAFE"
            android:padding="12dp"
            android:scaleType="centerInside"
            android:contentDescription="Аватар пользователя" />

        <View
            android:layout_width="16dp"
            android:layout_height="16dp"
            android:layout_gravity="bottom|end"
            android:background="@drawable/online_circle" />
    </FrameLayout>

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:layout_marginStart="14dp"
        android:orientation="vertical">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Alex Morgan"
            android:textColor="#0F172A"
            android:textSize="18sp"
            android:textStyle="bold" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="4dp"
            android:text="● В сети"
            android:textColor="#16A34A"
            android:textSize="13sp" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="4dp"
            android:text="Люблю игры и общение"
            android:textColor="#64748B"
            android:textSize="12sp" />
    </LinearLayout>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:paddingHorizontal="12dp"
        android:paddingVertical="8dp"
        android:text="Подписаться"
        android:textColor="#FFFFFF"
        android:textSize="12sp"
        android:textStyle="bold"
        android:background="#2563EB" />

</LinearLayout>


<!-- Задание 6. Статистика пользователя -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 6. Статистика пользователя"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="16dp"
    android:orientation="horizontal"
    android:gravity="center"
    android:background="#EFF6FF">

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center"
        android:orientation="vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="128"
            android:textColor="#1D4ED8"
            android:textSize="24sp"
            android:textStyle="bold" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Публикации"
            android:textColor="#475569"
            android:textSize="12sp" />
    </LinearLayout>

    <View
        android:layout_width="1dp"
        android:layout_height="42dp"
        android:background="#CBD5E1" />

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center"
        android:orientation="vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="2.4K"
            android:textColor="#1D4ED8"
            android:textSize="24sp"
            android:textStyle="bold" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Подписчики"
            android:textColor="#475569"
            android:textSize="12sp" />
    </LinearLayout>

    <View
        android:layout_width="1dp"
        android:layout_height="42dp"
        android:background="#CBD5E1" />

    <LinearLayout
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center"
        android:orientation="vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="356"
            android:textColor="#1D4ED8"
            android:textSize="24sp"
            android:textStyle="bold" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Подписки"
            android:textColor="#475569"
            android:textSize="12sp" />
    </LinearLayout>

</LinearLayout>


<!-- Задание 7. Карточка товара с индикатором -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 7. Карточка товара с индикатором"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="16dp"
    android:orientation="vertical"
    android:background="#FFFFFF">

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="150dp"
        android:background="#DBEAFE">

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:src="@android:drawable/ic_menu_gallery"
            android:scaleType="centerInside"
            android:contentDescription="Изображение товара" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="top|end"
            android:layout_margin="10dp"
            android:padding="6dp"
            android:text="ХИТ"
            android:textColor="#FFFFFF"
            android:textStyle="bold"
            android:textSize="12sp"
            android:background="#DC2626" />
    </FrameLayout>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="12dp"
        android:text="Беспроводные наушники"
        android:textColor="#0F172A"
        android:textSize="18sp"
        android:textStyle="bold" />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="4dp"
        android:text="2 490 ₽"
        android:textColor="#2563EB"
        android:textSize="20sp"
        android:textStyle="bold" />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="14dp"
        android:text="Популярность товара"
        android:textColor="#475569"
        android:textSize="13sp" />

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="8dp"
        android:layout_marginTop="6dp"
        android:background="#E2E8F0">

        <View
            android:layout_width="75%"
            android:layout_height="match_parent"
            android:background="#2563EB" />
    </FrameLayout>

</LinearLayout>


<!-- Задание 8. Экран настроек профиля -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 8. Экран настроек профиля"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="8dp"
    android:orientation="vertical"
    android:background="#FFFFFF">

    <!-- Личная информация -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="14dp"
        android:gravity="center_vertical"
        android:orientation="horizontal">

        <TextView
            android:layout_width="40dp"
            android:layout_height="wrap_content"
            android:text="👤"
            android:textSize="24sp"
            android:gravity="center" />

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:layout_marginStart="12dp"
            android:text="Личная информация"
            android:textColor="#0F172A"
            android:textSize="16sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="›"
            android:textColor="#64748B"
            android:textSize="28sp" />
    </LinearLayout>

    <View
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:background="#E2E8F0" />

    <!-- Уведомления -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="14dp"
        android:gravity="center_vertical"
        android:orientation="horizontal">

        <TextView
            android:layout_width="40dp"
            android:layout_height="wrap_content"
            android:text="🔔"
            android:textSize="24sp"
            android:gravity="center" />

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:layout_marginStart="12dp"
            android:text="Уведомления"
            android:textColor="#0F172A"
            android:textSize="16sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="›"
            android:textColor="#64748B"
            android:textSize="28sp" />
    </LinearLayout>

    <View
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:background="#E2E8F0" />

    <!-- Безопасность -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="14dp"
        android:gravity="center_vertical"
        android:orientation="horizontal">

        <TextView
            android:layout_width="40dp"
            android:layout_height="wrap_content"
            android:text="🔒"
            android:textSize="24sp"
            android:gravity="center" />

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:layout_marginStart="12dp"
            android:text="Безопасность"
            android:textColor="#0F172A"
            android:textSize="16sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="›"
            android:textColor="#64748B"
            android:textSize="28sp" />
    </LinearLayout>

    <View
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:background="#E2E8F0" />

    <!-- Помощь --><LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="14dp"
        android:gravity="center_vertical"
        android:orientation="horizontal">

        <TextView
            android:layout_width="40dp"
            android:layout_height="wrap_content"
            android:text="❓"
            android:textSize="24sp"
            android:gravity="center" />

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:layout_marginStart="12dp"
            android:text="Помощь и поддержка"
            android:textColor="#0F172A"
            android:textSize="16sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="›"
            android:textColor="#64748B"
            android:textSize="28sp" />
    </LinearLayout>

</LinearLayout>


<!-- Задание 9. Экран чата -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 9. Экран чата"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="340dp"
    android:layout_margin="8dp"
    android:orientation="vertical"
    android:background="#F8FAFC">

    <!-- Верхняя панель чата -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="60dp"
        android:orientation="horizontal"
        android:gravity="center_vertical"
        android:paddingHorizontal="16dp"
        android:background="#2563EB">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="‹"
            android:textColor="#FFFFFF"
            android:textSize="32sp" />

        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:layout_marginStart="16dp"
            android:orientation="vertical">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Алекс"
                android:textColor="#FFFFFF"
                android:textSize="17sp"
                android:textStyle="bold" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="в сети"
                android:textColor="#DBEAFE"
                android:textSize="12sp" />
        </LinearLayout>
    </LinearLayout>

    <!-- Область сообщений -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:orientation="vertical"
        android:padding="12dp">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="start"
            android:layout_marginTop="12dp"
            android:padding="12dp"
            android:text="Привет! Как дела?"
            android:textColor="#0F172A"
            android:textSize="14sp"
            android:background="#E2E8F0" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="end"
            android:layout_marginTop="12dp"
            android:padding="12dp"
            android:text="Привет! Всё отлично 😊"
            android:textColor="#FFFFFF"
            android:textSize="14sp"
            android:background="#2563EB" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="start"
            android:layout_marginTop="12dp"
            android:padding="12dp"
            android:text="Поиграем вместе?"
            android:textColor="#0F172A"
            android:textSize="14sp"
            android:background="#E2E8F0" />
    </LinearLayout>

    <!-- Поле ввода -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="56dp"
        android:orientation="horizontal"
        android:gravity="center_vertical"
        android:paddingHorizontal="8dp"
        android:background="#FFFFFF">

        <EditText
            android:layout_width="0dp"
            android:layout_height="44dp"
            android:layout_weight="1"
            android:hint="Сообщение..."
            android:singleLine="true"
            android:textSize="14sp"
            android:paddingHorizontal="12dp"
            android:background="#F1F5F9"
            android:inputType="textCapSentences" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginStart="8dp"
            android:padding="8dp"
            android:text="➤"
            android:textColor="#2563EB"
            android:textSize="22sp" />
    </LinearLayout>

</LinearLayout>

<img width="1918" height="814" alt="image" src="https://github.com/user-attachments/assets/bf8acb5e-01e7-4faa-8930-5a3225ae035b" />
roid:textSize="14sp"
            android:textStyle="bold" />
    </LinearLayout>

    <View
        android:layout_width="match_parent"
        android:layout_height="1dp"
        android:layout_marginTop="20dp"
        android:layout_marginBottom="14dp"
        android:background="#CBD5E1" />

    <!-- Стоимость товаров -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Товары"
            android:textColor="#64748B"
            android:textSize="14sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="3 280 ₽"
            android:textColor="#0F172A"
            android:textSize="14sp" />
    </LinearLayout>

    <!-- Доставка -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:orientation="horizontal">

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Доставка"
            android:textColor="#64748B"
            android:textSize="14sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="250 ₽"
            android:textColor="#0F172A"
            android:textSize="14sp" />
    </LinearLayout>

    <!-- Итоговая сумма -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:orientation="horizontal"
        android:gravity="center_vertical">

        <TextView
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Итого"
            android:textColor="#0F172A"
            android:textSize="20sp"
            android:textStyle="bold" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="3 530 ₽"
            android:textColor="#2563EB"
            android:textSize="22sp"
            android:textStyle="bold" />
    </LinearLayout>

    <!-- Кнопка оформления -->
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:padding="15dp"
        android:gravity="center"
        android:text="Оформить заказ"
        android:textColor="#FFFFFF"
        android:textSize="16sp"
        android:textStyle="bold"
        android:background="#2563EB" />

</LinearLayout>

<img width="1918" height="803" alt="image" src="https://github.com/user-attachments/assets/5e2df5fe-0e5c-4ff9-aa6f-5a9b15cff327" />
<!-- Задание 11. Каталог товаров -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Задание 11. Каталог товаров"
    android:textSize="20sp"
    android:textStyle="bold"
    android:textColor="#172554"
    android:padding="8dp" />

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:padding="12dp"
    android:orientation="vertical"
    android:background="#F8FAFC">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Каталог"
        android:textSize="24sp"
        android:textStyle="bold"
        android:textColor="#0F172A" />

    <EditText
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_marginTop="12dp"
        android:hint="Найти товар..."
        android:singleLine="true"
        android:paddingHorizontal="12dp"
        android:textSize="14sp"
        android:background="#E2E8F0"
        android:inputType="text" />

    <GridLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="12dp"
        android:columnCount="2"
        android:rowCount="2"
        android:useDefaultMargins="true">

        <!-- Товар 1 -->
        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_columnWeight="1"
            android:orientation="vertical"
            android:padding="10dp"
            android:background="#FFFFFF">

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="90dp"
                android:src="@android:drawable/ic_menu_gallery"
                android:background="#DBEAFE"
                android:scaleType="centerInside"
                android:contentDescription="Кроссовки" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="8dp"
                android:text="Кроссовки"
                android:textColor="#0F172A"
                android:textSize="15sp"
                android:textStyle="bold" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="4 990 ₽"
                android:textColor="#2563EB"
                android:textSize="14sp" />
        </LinearLayout>

        <!-- Товар 2 -->
        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_columnWeight="1"
            android:orientation="vertical"
            android:padding="10dp"
            android:background="#FFFFFF">

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="90dp"
                android:src="@android:drawable/ic_menu_gallery"
                android:background="#F3E8FF"
                android:scaleType="centerInside"
                android:contentDescription="Рюкзак" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="8dp"
                android:text="Рюкзак"
                android:textColor="#0F172A"
                android:textSize="15sp"
                android:textStyle="bold" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="2 490 ₽"
                android:textColor="#2563EB"
                android:textSize="14sp" />
        </LinearLayout>

        <!-- Товар 3 -->
        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_columnWeight="1"
            android:orientation="vertical"
            android:padding="10dp"
            android:background="#FFFFFF">

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="90dp"
                android:src="@android:drawable/ic_menu_gallery"
                android:background="#DCFCE7"
                android:scaleType="centerInside"
                android:contentDescription="Часы" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="8dp"
                android:text="Часы"
                android:textColor="#0F172A"
                android:textSize="15sp"
                android:textStyle="bold" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="3 790 ₽"
                android:textColor="#2563EB"
                android:textSize="14sp" />
        </LinearLayout>

        <!-- Товар 4 -->
        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_columnWeight="1"
            android:orientation="vertical"
            android:padding="10dp"
            android:background="#FFFFFF">

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="90dp"
                android:src="@android:drawable/ic_menu_gallery"
                android:background="#FEF3C7"
                android:scaleType="centerInside"
                android:contentDescription="Наушники" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="8dp"
                android:text="Наушники"
                android:textColor="#0F172A"
                android:textSize="15sp"
                android:textStyle="bold" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="2 190 ₽"
                android:textColor="#2563EB"
                android:textSize="14sp" />
        </LinearLayout>

    </GridLayout>
</LinearLayout>







