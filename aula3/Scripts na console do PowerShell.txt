# Para acessarmos o endereço do profile vigente no contexto do PowerShell, podemos
# usar a variável $profile.
# Note que nem sempre este arquivo existe!
$profile

# Podemos criar um novo Profile com o comando
New-Item $profile

# Sem nenhuma configuração inicial, não poderemos executar um script do PowerShell
# por conta das políticas de execução. Podemos saber mais sobre isso executando:
Get-Help about_ExecutionPolicy

# Para obtermos a política de execução corrente, usamos...
Get-ExecutionPolicy

# ...e para mudarmos seu valor (é necessário rodas o powershell como administrador)
Set-ExecutionPolicy Unrestricted

# Coringas também funcionam no comando Get-Help!
Get-Help about_*

Get-Help about_profiles

# Verificando o local onde deve ser armazenado o script de profile para todos os usuários e todos os hosts
$Profile.AllUsersAllHosts

New-Item $Profile.AllUsersAllHosts
notepad $Profile.AllUsersAllHosts







