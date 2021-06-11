# SPOVM
БГУИР ФКСиС ВМСиС 4 семестр

Лабораторные работы СПОВМ

[Лабораторная работа №1 : Запуск дочернего процесса](№1)

Для каждого процесса предусмотрена своя область вывода, в которой он выводит текущее системное время.

[Лабораторная работа №2 : Синхронизация процессов с помощью событий](№2)

Начальный процесс является управляющим. Он принимает поток ввода с клавиатуры и контролирует дочерние процессы. 
По нажатию клавиши ‘+’ добавляется новый процесс, ‘-’ – удаляется последний добавленный, ‘q’ – программа завершается.
Каждый дочерний процесс посимвольно выводит на экран в вечном цикле свою уникальную строку.
При этом операция вывода строки должна быть атомарной,
т.е. процесс вывода должен быть синхронизирован таким образом, чтобы строки на экране не перемешивались.

[Лабораторная работа №3 : Синхронизация работы с каналом через семафор](№3)

Создаются два процесса: клиентский и серверный. Серверный процесс ждет ввода пользователем текстовой строки
и по нажатию клавиши Enter производит следующие действия:
• клиентский процесс уведомляется о том, что серверный процесс готов начать передачу данных (синхронизация);
• серверный процесс передает полученную от пользователя строку клиентскому процессу, используя канал;
• клиентский процесс выводит полученную строку на экран и уведомляет серверный процесс об успешном получении строки;
• серверный процесс ожидает ввода следующей строки и т.д.

[Лабораторная работа №4 : Синхронизация потоков с помощью критической секции](№4)

Аналогично лабораторной работе No2, но с реализацией с помощью потоков.

[Лабораторная работа №5 : Использование динамической библиотеки](№5)

В каталоге имеется набор текстовых файлов. Разрабатываемое приложение состоит из двух потоков, которые работают по следующей схеме:

1) первый поток (читатель) асинхронным образом считывает содержимое одного файла;
2) поток-читатель уведомляет второй поток (писатель) о том, что содержимое файла прочитано и может быть передано писателю;
3) поток-писатель получает от первого потока содержимое файла и асинхронным образом записывает полученную строку в конец выходного файла;
4) поток-писатель уведомляет читателя о том, что строка записана в выходной файл и можно приступать к чтению следующего файла;
5) процедура повторяется с п.1, пока не закончится список файлов. В результате должна быть произведена конкатенация (объединение) 
входных текстовых файлов в один результирующий.

Функции чтения-записи должны быть выделены в динамическую библио-
теку, подключены на этапе выполнения программы и выгружены после отра-
ботки основного цикла.
