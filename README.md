# bestGuida
 # 1. Избегайте глобальных переменных
      Сведите к минимуму использование глобальных переменных.
      Проблема с глобальными переменными и функциями заключается в том, что они могут быть перезаписаны другими скриптами.
      Вы можете обернуть все это анонимной функцией. Или используйте литерал объекта.
 # 2. Установите приоритет доступа к локальным переменным
      JavaScript сначала выполняет поиск, чтобы увидеть, существует ли переменная локально, а затем постепенно выполняет поиск на более высоких уровнях области видимости до глобальных переменных. Поэтому локальные переменные будут найдены быстрее.
      Чтобы определить текущую область видимости, перед каждой переменной ставьте let или const . Это предотвратит поиск, а также ускорит код.
 # 3.Объявления сверху
     Поместите все объявления поверх сценария или функции, чтобы получить более чистый код. Вы не хотите, чтобы объявления были по всему коду. И вы хотите уменьшить возможность повторных заявлений.

 # 4.Используйте === Сравнение
     При использовании ==ваши переменные будут преобразованы в типы соответствия.
    0 == "" ; // истина
    0 === "" ; // ложный
    0 == «»; Это даст истину.
    Где 0 === «»; произведет ложь.
    Это потому, ===что оператор вызывает сравнение значений и типов.

 # 5. Не объявляйте ненужные переменные
      Больше переменных, больше места в памяти.
Например, вместо того, чтобы писать это:
    const sidebar = sidebar.querySelector ('# боковая панель');
    const параграф = foo.querySelector ('p');
    paragraph.textContent = 'foo';
Вы можете написать это:
    document.querySelector ('# боковая панель p'). textContent = 'foo';
В первом случае у нас было две переменные. После небольшой реструктуризации у нас теперь нет переменных.

 # 6.Не используйте новый объект ()
    Используйте {}вместоnew Object()
    Используйте ""вместоnew String()
    Используйте 0вместоnew Number()
    Используйте falseвместоnew Boolean()
    Используйте []вместоnew Array()
    Используйте /()/вместоnew RegExp()
    Используйте function (){}вместоnew Function()
Преимущества:
    код короче и читабельнее
    код безопаснее. Литералы по-прежнему будут работать, когда Objectконструкторы были переопределены
    это немного быстрее

 # 7.Используйте самый быстрый способ перебора переменных
    В JavaScript есть много способов перебрать Array.
    Первый способ - forпетля. Другие способы включают for...ofцикл, forEachметод массивов. mapи filter.Кроме того, перебирайте массив по мере выполнения операций карты и фильтрации. И еще есть whileпетля.
    forЦикл является самым быстрым способом. Кэширование lengthулучшает работу цикла.
    пусть arrayLength = array.length;
    for (let i = 0; i <arrayLength; i ++) {
       let val = array [i];
    }
    Некоторые браузерные движки оптимизировали forцикл без кеширования свойства length.
    whileЦикл с декремента индекса примерно в 1,5 раза медленнее , чем forпетли
    Использование forEachцикла в 10 раз медленнее, чем forцикл, поэтому, вероятно, лучше его избегать, особенно для больших массивов.
 # 8.Не делайте слишком много вложений
    Слишком большое вложение может сделать ваш код нечитаемым. Кодировщик за вами не должен страдать, когда их редакторы кода переносят длинные строки.
    firstFunction ( args , function () {
        secondFunction ( args , function () {
            thirdFunction ( args , function () {
                // И так далее…
             });
         });
    });
 # 9.Не передавайте строку в "SetInterval" или " SetTimeOut"
    Если передавать само выражение функции вSetInterval или SetTimeOut, то это снижает эффективность и читабельность кода. Поэтому следует передавать только имя функции

 Bad

    setInterval(
    "document.getElementById('container').textContent = 'Добро пожаловать!'", 3000
    );
 Good

    const writeContext = function() {
      const container = document.getElementById('container');
      container.textContent = 'Добро пожаловать!'
    }
    setInterval(writeContext, 3000);

 # 10.Прокомментируйте Свой Код
    Пишите хорошую документацию к своему коду — тогда тот, кто столкнётся с ним в будущем, поймёт, что и почему в этом коде делается.

 Bad

    const isPositive = arr.every(item => item > 0);
    console.log(isPositive(arr));
 Good

    //функция проверяет все ли элементы массива положительные
    const isPositive = arr.every(item => item > 0);
    console.log(isPositive(arr));
