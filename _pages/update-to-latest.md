---
permalink: /update-to-latest.html
title: Безопасное обновление прошивки 
author_profile: true
---
{% include toc title="Разделы" %}

Эта страница предназначена только для обновления SX OS! Если вы прешли сюда обновлять Atmosphere, то [делайте это по соответствующему гайду](https://switch.customfw.xyz/update-to-latest)
{: .notice--warning}

Никогда не обновляйте SysNAND этим методом! Он предназначен **только** для использования EmuNAND! SysNAND обновляется **только** стандартным способом, через настройки! Обновивши SysNAND через ChoiDujourNX на Mariko, вы гарантированно получите брик при попытке зайти в SysNAND! 
{: .notice--danger}

SXOS, а значит и KEFIR4, будут работать только на приставке с прошивкой 11.0.0 или ниже!
{: .notice--warning} 

## Что понадобится

* [Kefir 4](https://github.com/rashevskyv/kefir/releases/tag/491){:target="_blank"}
* [Прошивка **{% include /vars/update_version.txt %}**](https://darthsternie.net/switch-firmwares/){:target="_blank"}
* Карта памяти 

## Инструкция

### Часть I - Резервное копирование EMUNAND

1. Выключите консоль и вставьте её карту памяти в ПК
1. Скопируйте на ПК папку `sxos/emunand`
	* Если обновление пройдёт успешно, можно будет удалить эту папку с ПК

### Часть II - Подготовка к обновлению

1. Выключите Switch и вставьте его карту памяти в ПК
1. Установите `.zip`-архив [Kefir 4](https://github.com/rashevskyv/kefir/releases/tag/491){:target="_blank"}, если ещё не делали этого
1. Распакуйте архив `{% include /vars/update_version.txt %}.zip` в любую удобную папку на карте памяти вашей приставки (например, папку `update`)
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

1. После окончания установки нажмите "**Reboot**", "**Shutdown**", чтобы выключить приставку. 
	* Имейте ввиду, что эмунанд перестанет загружаться после обновления! Продолжайте выполнять инструкцию по миграции, чтобы это исправить

___

[Закрыть страницу](javascript:window.close();)
{: .notice--success}