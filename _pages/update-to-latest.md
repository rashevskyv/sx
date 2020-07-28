---
permalink: /update-to-latest.html
title: Безопасное обновление прошивки 
author_profile: true
---
{% include toc title="Разделы" %}

## Что понадобится

* Свежая версия {% include abbr/kefir_addr.txt %}
* Прошивка {% include /vars/update_version.txt %} (скачайте по любой из ссылок):
	* [magnet](magnet:?xt=urn:btih:B23F438BA3FED6462C067496F14D37D88B46BEF8&dn=10.1.0.zip&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce){:target="_blank"}
	* [ЯД](https://yadi.sk/d/BzsYZLjroSgLjw){:target="_blank"}
	* [GD](https://drive.google.com/file/d/10L8zKy-Js9L3QyljOqBJLz-zTXDTxofO/view?usp=sharing){:target="_blank"}
	* [MEGA](https://mega.nz/file/Bt1h3QpD#oCQVvmE57c_RNveZIl1wVZ30ktposLsUrUoEMIgcKk8){:target="_blank"}

## Инструкция

### Часть I - Резервное копирование EMUNAND

1. Выключите консоль и вставьте её карту памяти в ПК
1. Скопируйте на ПК папку `sxos/emunand`
	* Если обновление пройдёт успешно, можно будет удалить эту папку с ПК

### Часть II - Подготовка к обновлению

1. Выключите Switch и вставьте его карту памяти в ПК 
1. Удалите следующие папки с карты памяти, если таковые имеются:
	* `sxos/titles/0100000000001000`
	* `sxos/titles/0100000000001013`
	* `sxos/titles/0100000000000352`
1. Установите `.7z`-архив {% include abbr/kefir_addr.txt %}, если ещё не делали этого
1. Скопируйте **содержимое** архива `{% include /vars/update_version.txt %}.zip` с прошивкой в корень карты памяти
	* Ещё раз - **содержимое** архива **с прошивкой**. Не архив с кефиром, **с прошивкой**! Архив с прошивкой расположен в части [Что понадобится](#что-понадобится). Нужно скопировать не сам архив, а именно его **содержимое**
	* Вместо этого вы можете скачать архив со свежей версией системного ПО через приложение **FreshHay** прямо на вашей приставке. Для этого запустите [HBL](hbl){:target="_blank"} через игру, выберите приложение **FreshHay** и нажмите (A), чтобы начать закачку прошивки. Программа сама скачает последнюю версию системного ПО в папку `switch/FreshHay`. После, распакуйте скачанный архив с помощью **NXShell**. Архив будет находиться по пути `switch/Freshhay`
1. Вставьте карту памяти обратно в приставку

### Часть III - Обновление прошивки

1. Запустите приставку
1. Запустите **Альбомы**, чтобы попасть в **Homebrew Launcher**

    ![]({{ base_path }}/images/screenshots/gallery.jpg) 
    {: .text-center}
    {: .notice--info}

1. Запустите **ChoiDujourNX**
1. Перейдите в папку, в которой находится прошивка {% include /vars/update_version.txt %}, скопированная ранее, и нажмите "**Choose**"

	![]({{ base_path }}/images/screenshots/choi/fw.png)
	{: .text-center}

	![]({{ base_path }}/images/screenshots/choi/choose.png)
	{: .text-center}

1. Выберите "**{% include /vars/update_version.txt %} (exFAT)**"

	![]({{ base_path }}/images/screenshots/choi/exfat.png)
	{: .text-center}

1. Дождитесь окончания обработки прошивки и нажмите "**Select firmware**"
	
	![]({{ base_path }}/images/screenshots/choi/select_fw.png)
	{: .text-center}

1. Дождитесь окончания распаковки прошивки и нажмите "**Start installation**"
	
	![]({{ base_path }}/images/screenshots/choi/start.png)
	{: .text-center}

	* При установки прошивки с такой же версией, как исходная (например, у вас стоит {% include /vars/update_version.txt %}, а вы пытаетесь установить {% include /vars/update_version.txt %} (exFAT)) может возникать ошибка. В таком случае, вам придётся установить прошивку с версией ниже (например, если у вас сейчас стоит 10.0.2, поставьте 9.2.0), а уже потом повышать её. 
	* Если вы попали в такую ситуацию, обязательно сделайте бекап перед обновлением!
1. После окончания установки нажмите "**Reboot**", "**Reboot now**", чтобы перезагрузить приставку. 
	* Если приставка загрузилась и в Системные настройки -> Система отображается обновленная версия системного ПО, то вы можете удалить ранее сделанный бекап EmuNAND с ПК, а так же папку с прошивкой с вашей карты памяти

## Важно знать

* Если после прошивки вам предложат обновить контроллеры - обновляйте
* Если после обновления у вас чёрный экран после логотипа Nintendo, удалите с карты памяти папку `sxos/emunand` и скиньте на карту копию EmuNAND, что вы делали ранее.

___

[Закрыть страницу](javascript:window.close();)
{: .notice--success}