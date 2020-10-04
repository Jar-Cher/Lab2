# Лабораторная работа №2. Activity Lifecycle. Alternative resources.
## Цели:
* Ознакомиться с жизненным циклом Activity.
* Изучить основные возможности и свойства Alternative resources.


## Задания (19 вариант):
### Задание 1. Activity.
В задании сказано продемонстрировать жизненный цикл Activity на любом нетривиальном примере, где тривиальным примером считаются: создание/открытие/закрытие приложения (кроме случаев нестандартного завершения работы: SIGKILL, Force Stop, etc.), а также поворот экрана.
Я изменил дефолтный MainActivity, чтобы в консоль выводились уведомления при вызове основных методов жизненного цикла приложения:
Как и предполагалось:
*	При открытии приложения выводятся уведомления:

![Иллюстрация к проекту](ReportData/1.png)
*	Приход сообщения, звонок и просмотр экрана уведомлений не привели ни к каким целевым уведомлениям в консоли.
*	Выход «домой»:

![Иллюстрация к проекту](ReportData/2.png)
*	При открытии приложения через список ранее запущенных:

![Иллюстрация к проекту](ReportData/3.png)
*	При выключении экрана:

![Иллюстрация к проекту](ReportData/4.png)
*	При включении экрана:

![Иллюстрация к проекту](ReportData/5.png)

### Задание 2. Alternative Resources.
19ый вариант преобразуется в 4ый - "Available height". 


## Листинги:
### Задание 1, MainActivity
'''
package com.example.lab1

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import com.example.lab2.R

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d("CREATION", "Created!")
    }

    override fun onStart() {
        super.onStart()
        Log.d("START", "Started!")
    }

    override fun onRestart() {
        super.onRestart()
        Log.d("RESTART", "Restarted!")
    }

    override fun onPause() {
        super.onPause()
        Log.d("PAUSE", "Paused!")
    }

    override fun onResume() {
        super.onResume()
        Log.d("RESUME", "Resume!")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("DESTROY", "Destroyed!")
    }

    override fun onStop() {
        super.onStop()
        Log.d("STOP", "Stopped!")
    }
}
'''