<h1>КОМАНДНЫЙ ПРОЕКТ для лабораторной работы №12 по дисциплине "Основы программной инженерии"

<h2>СТРУКТУРА ПРОЕКТА</h2>

<h3>Если кратко:</h3>
<p>
В main() есть главное меню, в котором пользователь может выбрать вариант выполнения программы. Для решения своей задачи из лр 12 нужно написать одну функцию типа void (при необходимости она может вызывать подфункции). Эта функция будет вызываться из main(), если пользователь выберет в главном меню соответствующий вариант действия. Каждый член команды создаст один заголовочный файл .h с прототипом(-ами) своей(-их) функции(-й) (прототипы подфункций тоже там) и один файл реализации .cpp с определениями всех своих функций из .h. Эти два файла нужно будет отправить сюда, на удалённый репозиторий (как это сделать? - описано ниже).
</p>

<h3>Проект содержит в себе:</h3>
<ul>
  <li> Файл main.cpp с главным меню программы</li>
  <li> Заголовочный файл (.h) для каждого решения задания из лр 12</li>
  <li> Файл реализации (.cpp) для каждого решения задания из лр 12</li>
</ul>

<h4>main.cpp</h4>
<p>
Главный файл программы. В начале файла прописываются директивы #include для подключения заголовочных файлов. При запуске программы отображается меню с выбором дальнейших действий (каждый вариант выбора - одно из заданий лр 12), также есть вариант завершить выполнение программы.
</p>

<h4>Заголовочные файлы</h4>
<p>
Для каждого задания нужно создать один файл заголовка и один файл реализации. Имя файла заголовка практически совпадает с именем функции для выполнения задания (эта функция вызывается из главного меню в main() ).<br>
<i>Пример:</i> если функция задания имеет имя stringCalculator, то заголовочный файл будет иметь имя string_calculator(.h)<br>
Файл заголовка должен иметь следующую структуру:<br>
    <pre>
    #ifndef ИМЯ_ФАЙЛА_ЗАГОЛОВКА_H
    #define ИМЯ_ФАЙЛА_ЗАГОЛОВКА_H<br>
    // Здесь перечисляются прототипы (объявления) всех функций, используемых в файле реализации (без определений этих функций).<br>
    #endif</pre>
</p>

<h4>Файлы реализации</h4>
<p>
Вместе с заголовочным файлом нужно создать файл реализации, где будут определены функции, описанные в файле заголовка. Имя файла реализации полностью совпадает с именем соответствующего заголовка, за исключением расширения .cpp вместо .h<br>
<i>Пример:</i> если функция задания имеет имя stringCalculator, то файл реализации будет иметь имя string_calculator(.cpp)<br><br>
В зависимости от задания, файл реализации имеет одну из двух следующих структур:<br>
<br>
1) Если задача условно неделима, то сначала выполняется основная функция задачи, затем выводится меню выбора: выполнить задачу ещё раз, выйти в меню или выйти из программы.<br>
<i>Пример: задача - вывод текущего времени.</i><br>
Пользователь в главном меню (в main() ) выбирает вариант "вывести текущее время", main() вызывает функцию void currentTime() (прототип функции в current_time.h, реализация в current_time.cpp), функция сначала выводит текущее время, затем выводит меню выбора: вывести текущее время (т.е. снова), перейти в меню или выйти из программы. <b>Шаблон кода: см. testFunc1.h и testFunc1.cpp</b><br>
<br>
2) Если задача делимая, т.е. если пользователь сразу выбирает, что будет делать программа, то сначала выводится меню выбора: выполнить первую подзадачу, выполнить вторую подзадачу, выйти в меню или выйти из программы - и только потом выполняется подзадача. Обратите внимание: в первом случае сначала хотя бы раз выполняется задача, во втором можно вернуться в меню до выполнения задачи.<br>
<i>Пример: задача - перевод числа из двоичной системы счисления в десятичную и наоборот.</i><br>
Пользователь в главном меню (в main() ) выбирает вариант "перевести число из...", main() вызывает функцию void binDecConverter() (прототип функции в bin_dec_converter.h, реализация в bin_dec_converter.cpp), функция сначала выводит меню выбора: перевести число из 2-й сист. сч. в 10-ую,  перевести число из 10-й сист. сч. в 2-ую, перейти в меню или выйти из программы - и потом, после выбора пользователя, выполняется перевод введённого числа в нужную систему счисления. <b>Шаблон кода: см. testFunc2.h и testFunc2.cpp</b><br>
<br>
<b>Это необязательно</b>, но мне кажется, что реализация циклического выполнения вашей функции с возможностью перейти в меню или выйти из программы удобнее автоматического завершения функции с выходом в меню. Так или иначе, если это не сделаете вы, это сделаю я. Но вы можете сделать мою жизнь чуточку проще.  
</p>

<h2>Начало работы</h2>
<p>Чтобы начать работу над своим заданием, нужно:<br>
  <ol>
    <li>
      <ul><b>Клонировать себе этот репозиторий</b>
        <li>Запустить Visual Studio</li>
        <li>Нажать "Клонирование репозитория"</li>
        <li>Дальше нужно ввести ссылку на этот репозиторий ( https://github.com/Aliaksiej-Ramanchuk/emap ) и указать (создать) пустую папку, куда будет клонирован репозиторий</li>
        <li>Нажать "Клонировать"</li>
      </ul>
    </li>
    <li>
      <ul><b>Найти файлы полученного проекта</b>
        <li>Дважды нажать в обозревателе решений на emap.sln (в папке решения будут все нужные файлы проекта)</li>
      </ul>
    </li>
    <li>
      <ul><b>Выполнить своё задание</b>
        <li>На всякий случай (если кто-то ко времени начала вашей работы успел отправить на репозиторий изменения, а у вас их нет) в меню Visual Studio найдите и откройте вкладку Git (в самом верху, между Вид и Проект) и в выпадающем меню выберите "Получить" (забрать последние изменения).
        <li>Добавить в проект файл заголовка и файл реализации для функции, выполняющей ваше задание</li>
        <li>Собственно написать свои файлы заголовка (один файл с прототипами всех ваших функций) и реализации (один файл со всеми определениями функций)</li>
        <li>В главном файле main.cpp добавить <code>#include "имя_заголовочного_файла.h"</code></li>
        <li>В функции main(), где идут switch-case'ы, в соответствующем case прописать название своей функции (она будет вызываться из этого главного меню)</li>
        <li>
          <ul>Проверить, что...
            <li>...ничего не падает</li>
            <li>...задача выполнена (хотя бы частично, но доделать потом)</li>
            <li>...есть надёжная защита от некорректного ввода (с std::cin используйте char или std::string, а не int/double и обрабатывайте ввод как текст). Не получается? Оставьте как есть, сам подправлю</li>
            <li>...стиль написания кода такой же, как и в остальном проекте (camelCase для переменных и функций, UPPER_CASE для констант, snake_case для файлов, везде одинаково расставлены пробелы, переносы строк, все переменные (за исключением, может, итераторов) и функции имеют <u>осмысленные</u> имена и т.д. и т.п.).</li>
          </ul>
        </li>
        <li><b>Всё равно ничего не понятно? - сделайте хоть что-нибудь хоть как-нибудь, а я подправлю. Не затягивайте!</b></li>
      </ul>
    </li>
    <li>
      <ul><b>Сохранить и отправить свои изменения на удалённый репозиторий (сюда)</b>
        <li>Снова откройте вкладку Git</li>
        <li>В выпадающем меню нажмите "Фиксация или скрытие", чтобы создать локальный коммит</li>
        <li>Справа нужно написать комментарий к коммиту (там где "Введите сообщение <Required>")</li>
        <li>Нажмите "Зафиксировать все"</li>
        <li>Снова откройте вкладку Git, нажмите "Отправить"</li>
        <li>Если всё хорошо, то изменения уже применились в удалённом репозитории. Но может произойти и конфликт слияния: он решается вручную прямо в Visual Studio. Экран разделится на три области (что в удалённом репозитории, что в локальном и область решения конфликта) После решения конфликта нужно будет нажать "Принять слияние", зафиксировать и (кажется) снова отправить</li>
      </ul>
    </li>
  </ol>
</p>

<h2>Прочее, но <b>важное</b></h2>
<p>
Так получилось, что всю <b>документацию</b> проекта вёл, веду и буду вести я. Вы, главное, свои задания сделайте и отправьте сюда, на удалённый репозиторий. <b>Всю существующую документацию можно посмотреть на сайте проекта (файл emap.html).</b> Если не можете найти файл, его можно открыть прямо из главного меню программы проекта.<br>
<br>
Вообще говоря, сначала нужно было создать т.н. <b>бэклог продукта</b>, где будут описываться все требования к нашим функциям, и уже <i>на основе пользовательских историй</i> писать программу проекта. Эти истории (хоть и с небольшим опозданием) я написал, они <b>есть на сайте</b>. Синяя полоска слева от истории означает, что история выполнена, оранжевая - нет (ещё). Получилось что-то похожее на kanban-доску.<br>
<br>
<b>Бэклог спринта</b> мы делать не будем, т.к. никто не может сказать даже приблизительно, когда что сделает, а если учитывать, что я планирую покончить с проектом к понедельнику (в пн защитить), то бэклог спринта теряет смысл.<br>
<br>
<b>Диаграммы вариантов</b> для каждого модуля программы я взял на себя и уже сделал (на сайте проекта), но диаграммы для ещё не реализованных модулей/функций, возможно, нужно будет изменить, т.к. я не могу знать деталей реализации ещё не реализованного модуля.<br>
<br>
<b>Система тестов</b>. Тут нужно будет для каждого действия в программе написать последствия, разбив всё на шаги. Было бы хорошо, если бы вы сами написали небольшие системы тестов для своих программ, но делать вы это конечно же не будете, поэтому это опять-таки беру на себя я. Система тестов - единственное, чего ещё нет на сайте, но шаблон будет уже 9 декабря. Опять-таки, я не могу написать все шаги и результаты выполнения программы, пока вы не напишете и не отправите свои модули. Для системы тестов нужно изучить все мелочи кода модулей, а это <b>займёт время</b>, поэтому я ещё раз прошу сделать свои задания как можно скорее, чтобы к ночи с субботы на воскресенье мной была написана вся нужная документация. От вас мне нужен только код, я требую минимум. Постарайтесь, пожалуйста.<br>
</p>

<p> - Раманчук Аляксей</p>
