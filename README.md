# linux-kernel-5.0.1-griggorii-dbg-property-patent
kernel dbg property deb ubuntu debian

https://yadi.sk/d/Dwm303c88egAzg вес dbg тладки ядра имеет 6 Гигабайт

Это созданный  dbg отладчик его можно у меня приобрести за 5000000 рублей и репа с ним исчезает 
вы заниметесь отладкой делаете супер ядро которое не то что бы летает , а парит и никогда у него ничего не отказывает 
фирмы типа самсунг или другие шлите предложения по покупке dbg , кто скажет дорого пусть тогда вот тут не воруя создаст с нуля
исходников валяется полно , а время же ж и знания как это сделать то то , мне надо покупать оборудование для создания чего то 
нового и помещение

Вы можете поставить свою цену и перепродать dbg но что бы 5000000 были с вас как пере продавателя передачи авторских прав , как ниже указано это не аудио формат который точно можно взять и защититься конторками типа рекордс это реверс инженеринг

Alt + Q самый быстрый терминал для отладки пойдёт в самый раз

Не забываем так же что программы могут отреверсироваться и в них выйдут настоящие имена и ники создателей тогда уже от ответа 
купили у создателя , но не купили не проидут

Так же вы можете попробовать мои операционные системы надежная https://github.com/Griggorii/Cinnamon-Budgie-OS-4.0-beta-based-18.04
 и бета не совсем ещё надёжная https://github.com/Griggorii/Cinnamon-Budgie-OS-9.0-beta-based-19.04 
 
 В чём секрет многие зададуться вопросом , а секрет в том что в 18.10 переброшены вручную пакеты из образа который я создавал в 2016 году на базе 16.04.  Если проверить то на budgie панели есть допустим регулятор яркости и он рабочии потому что я мозг сломал , но перенес , так же у меня на запуск budgie-panel поставлена задержка в несколько секунд так как python3 не даёт загрузить значки 
 рабочего стола, сам python3 находится отдельным элементом и стартует из виджета времени и погоды, по этому по логике на панель я поставил задержку что бы дать nemo проводнику показать иконки.
 
Так же есть уже слепок операционных систем https://onedrive.live.com/?authkey=%21AEZC7hHiSM5gxkE&id=38111762B7A1295F%2112479&cid=38111762B7A1295F 5 андройд лучший , которая послужит первой сверх лёгкой операционной системой linux на десктопах потому что я оттуда вытащил гугл сервисы и всё остальное что перегружало телефон в упадок и зависание за место сервисов гугл тут можно использовать micro-g слепок я снял при помощи termux вот видео где можно посмотреть потроха https://www.youtube.com/watch?v=TxIdFsTLUVY вот такой вот командой tar cvpjf backup.tar.bz2 --exclude=/proc4 --exclude=/mnt --exclude=/sys / --exclude=/lost+found --exclude=/tmp --exclude=/backup.tar.bz2 т.е я первый в мире человек кто снял дамп прямо с андроидно линуксовой мобильной платформы в один фаил.
Android linux обычно всегда разделялся на несколько партиции , а тут он воедино в одном контейнере что поможет избавиться от такой не нужной технологии как несколько партиции.
Прошивку я заранее модифицировал поставил туда busy-box system/xbin и что бы там был рут иначе я не смогу со своей командой модифицировать и улучшать свою операционную систему.
Перенос системы на ПК я представлю так system это и есть тот самый /  ну в общем такой папки system не должно быть это раздел который мы как бы можем обозвать типа sblive или вообще не обзывать и удалить название раздела т.е это /
Там уже есть termux который сам сабя упаковал в структуру т.е я заранее обеспокоился что бы там был терминал и su бинарник.
Было снято с платформы mtk6572

Я даже знаю приблизительно что у меня сдернули сборку и уже упаковали надо искать фаил rpm с назнанием cm-x86-14.1-r2  rpm и
от рута его распаковать в корень ситемы , в итоге в системе надо найти папку от рута cm-x86-14.1-r2 потом в /boot/grub поместить фаил custom.cfg следующего заполнения как указано ниже и затем обновить grub

Пример custom.cfg

_______________________________________________________________________________________________________________________________

menuentry "Android-x86 14.1-r2" {

	search --set=root --file /cm-x86-14.1-r2/kernel
	
	linux /cm-x86-14.1-r2/kernel quiet root=/dev/ram0 androidboot.selinux=permissive vmalloc=192M buildvariant=userdebug 
	
	initrd /cm-x86-14.1-r2/initrd.img
	
}
menuentry "Android-x86 14.1-r2 (DEBUG mode)" {

	search --set=root --file /cm-x86-14.1-r2/kernel
	
	linux /cm-x86-14.1-r2/kernel root=/dev/ram0 androidboot.selinux=permissive vmalloc=192M buildvariant=userdebug DEBUG=2
	
	initrd /cm-x86-14.1-r2/initrd.img
	
}
_______________________________________________________________________________________________________________________________

Вот только лучше бы они андроид 5 взяли чем натягивать внутрь лего этот же андройд пять что бы окошки были квадратные

Что бы этот же андроид сохранял изменения в папке создать фаил data.img естественно можно создать и переместить внутрь папки 
cm-x86-14.1-r2 пример создания такого data.img размером 20 гигабайт , если у вас мало места то ставьте за место 20 любую цифру меньше

dd if=/dev/zero of=data.img bs=1 count=0 seek=20G

mkfs.ext4 data.img
