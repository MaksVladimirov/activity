# activity
Activity
Запуск приложения
2025-02-19 21:09:28.087 3269-3269 MainActivityLifecycle com.example.businesscard D onCreate called
2025-02-19 21:09:28.242 3269-3269 MainActivityLifecycle com.example.businesscard D onStart called
2025-02-19 21:09:28.249 3269-3269 MainActivityLifecycle com.example.businesscard D onResume called

onCreate() вызывается первым, так как Activity нужно сначала создать.
onStart() вызывается после, потому что Activity теперь готова к отображению.
onResume() вызывается последним, так как Activity теперь готова к взаимодействию с пользователем.
Поворот экрана
2025-02-19 21:11:37.063 3269-3269 MainActivityLifecycle com.example.businesscard D onPause called
2025-02-19 21:11:37.079 3269-3269 MainActivityLifecycle com.example.businesscard D onStop called
2025-02-19 21:11:37.087 3269-3269 MainActivityLifecycle com.example.businesscard D onSaveInstanceState called
2025-02-19 21:11:37.132 3269-3269 MainActivityLifecycle com.example.businesscard D onDestroy called
2025-02-19 21:11:37.192 3269-3269 MainActivityLifecycle com.example.businesscard D onCreate called
2025-02-19 21:11:37.235 3269-3269 MainActivityLifecycle com.example.businesscard D onStart called
2025-02-19 21:11:37.238 3269-3269 MainActivityLifecycle com.example.businesscard D onRestoreInstanceState called
2025-02-19 21:11:37.244 3269-3269 MainActivityLifecycle com.example.businesscard D onResume called

Когда происходит поворот экрана, Activity уничтожается и пересоздаётся. Это нужно, чтобы система могла подстроиться под новую ориентацию (например, изменить расположение элементов на экране).

Основной процесс:

Старая Activity закрывается:
onPause() → onStop() → onSaveInstanceState() → onDestroy()
Создаётся новая Activity:
onCreate() → onStart() → onRestoreInstanceState() → onResume()
**onPause() **

Вызывается перед тем, как Activity перестанет быть активной.
В этот момент пользовательский ввод уже не принимается, но UI ещё виден.
**onStop() **

Вызывается когда Activity становится невидимой.
Теперь приложение больше не отображается на экране.
**onSaveInstanceState() **

Вызывается перед уничтожением Activity, чтобы сохранить её состояние.
Позволяет сохранить текст в полях ввода, положение скролла, переменные.
**onDestroy() **

Activity полностью уничтожается.
Все её ресурсы освобождаются.
Свернуть приложение
2025-02-19 21:13:43.622 3269-3269 MainActivityLifecycle com.example.businesscard D onPause called
2025-02-19 21:13:44.423 3269-3269 MainActivityLifecycle com.example.businesscard D onStop called
2025-02-19 21:13:44.423 3269-3269 MainActivityLifecycle com.example.businesscard D onSaveInstanceState called

В отличие от поворота экрана, сворачивание приложения не уничтожает Activity. Android оставляет её в памяти, чтобы быстро восстановить при возврате.

onPause() → Activity теряет фокус, но остаётся видимой.
onStop() → Activity больше не видно, уходит в фон.
onSaveInstanceState() → Android сохраняет состояние, чтобы восстановить при возврате.
Развернуть приложение
2025-02-19 21:15:11.425 3269-3269 MainActivityLifecycle com.example.businesscard D onRestart called
2025-02-19 21:15:11.425 3269-3269 MainActivityLifecycle com.example.businesscard D onStart called
2025-02-19 21:15:11.426 3269-3269 MainActivityLifecycle com.example.businesscard D onResume called

onRestart() вызывается, когда приложение возвращается из фона. Это позволяет подготовить Activity перед её видимостью.
onStart() вызывается после, когда Activity становится видимой, но ещё не активной.
onResume() вызывается, когда Activity становится активной и готова к пользовательскому вводу.
Закрыть приложение
2025-02-19 21:16:43.409 4198-4198 MainActivityLifecycle com.example.businesscard D onPause called
2025-02-19 21:16:43.418 4198-4198 MainActivityLifecycle com.example.businesscard D onStop called
2025-02-19 21:16:43.420 4198-4198 MainActivityLifecycle com.example.businesscard D onSaveInstanceState called
2025-02-19 21:16:43.444 4198-4198 MainActivityLifecycle com.example.businesscard D onDestroy called

onPause() — приложение теряет фокус и переходит в фоновое состояние, но всё ещё не уничтожено.
onStop() — приложение больше не видно на экране, оно уходит в фоновый режим.
onSaveInstanceState() — перед остановкой Activity сохраняются данные, чтобы при необходимости восстановить их.
onDestroy() — после того, как Activity больше не нужна, она уничтожается, и ресурсы освобождаются.
Вызов метода finish
2025-02-19 21:18:16.831 4294-4294 MainActivityLifecycle com.example.businesscard D onCreate called
2025-02-19 21:18:17.655 4294-4294 MainActivityLifecycle com.example.businesscard D onDestroy called

onCreate() вызывается, когда создаётся новый экземпляр Activity.

onDestroy() вызывается, когда Activity завершена и освобождает все ресурсы. Это последняя стадия жизненного цикла перед её уничтожением.
