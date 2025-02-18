## Get-Execution Policy -List

```powershell-session
PS C:\Users\Lenovo\htb> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       Undefined
 ```

#### What scripts we can execute. 

**Remote Signed** means we can only run scripts that you write on your own.
Running scripts from the internet will require a **digital signature** from trusted source. 

If there is no signature: 
*File cannot be loaded because running scripts is disabled on this system"*

## Need to run Windows VM 
to continue....

