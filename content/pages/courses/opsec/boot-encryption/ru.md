title: Шифрование раздела /boot
slug: boot-encryption
parent: opsec
lang: ru

Обычно, если вы включаете [шифрование](/pages/encryption.html) при установке Linux, то шифруется лишь основной раздел диска, на котором хранятся ваши данные. В такой конфигурации остается одна теоретическая уязвимость: незашифрованный раздел `/boot`. Если *недоброжелатели* получат физический доступ к вашему устройству, то в принципе они могут внедрить туда вирус и через него получить доступ к основному разделу, когда вы снова введете пароль.

Лучшее решение этой проблемы – превентивное: зашифровать `/boot`. К сожалению, процесс слишком сложен, чтобы приводить здесь полную инструкцию, поэтому я просто сошлюсь на [соответствующую страницу ArchWiki](https://wiki.archlinux.org/title/dm-crypt/Encrypting_an_entire_system#Preparing_the_boot_partition), которая должна быть актуальна для большинства дистрибутивов.

Конечно, на крайний случай остается еще ленивое решение: если есть основания полагать, что к вашему устройству могли получить доступ *недоброжелатели*, то вместо того, чтобы включать его, следует стереть и пересоздать раздел `/boot`. Но нет никаких гарантий, что вы об этом узнаете, и поэтому крайне рекомендуется использовать превентивное решение.
