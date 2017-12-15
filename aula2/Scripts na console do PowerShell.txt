# Invocando um script .bat com o Command Precedence
.\reiniciaServicoSrv01.bat

# Imprimindo a variável de ambiente PATH na console
echo $env:path
# Também podemos simplesmente executar a expressão 
$env:path

# Como o PowerShell é orientado a objetos com .NET, podemos invocar o método GetType() em qualquer variável
$env:path.GetType()

# Podemos invocar o método Split da classe string na variável PATH!
$env:path.Split(';')

# Podemos usar o comando Get-Member para verificarmos as propriedades e os métodos dsponíveis no objeto
$env:path | Get-Member

# Conseguimos obter todos os apelidos de comandos (ALIAS) no PowerShell com o comando Get-Alias
Get-Alias

# Conseguimos obter todos os comandos no PowerShell com o comando Get-Command
Get-Command

# Com o argumento -Name, nós conseguimos filtrar os comandos que possuem rename no nome. (O asterisco atua como coringa para qualquer quantidade de caractere)
Get-Command -Name *rename*

# Obtendo ajuda do comando rename-item
Get-Help Name rename-item

# Com o SwitchArgument -WhatIf podemos saber o que o comando faria antes de executarmos-o
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat -WhatIf

# Sem o SwitchArgument, tudo funciona normalmente
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat 

# Atualizamos os tópicos de ajuda do PowerShell com o comando Update-Help
Update-Help

# Obtemos todos os scripts que atuam com Aliases, com o comando "Get-Command -noun alias"
Get-Command -noun alias

# O Get-Help retorna a ajuda ou a sintaxe de um comando, quando um documento de ajuda não estiver disponível
Get-Help new-alias

# Com new-alias podemos criar novos aliases
new-alias -Name="rename" rename-item

#Podemos verificar nosso alias criado com o comando abaixo
get-alias rename

#Alias feito, agora podemos executar!
rename C:\Scripts\script.bat C:\Scripts\script_migrando.bat 