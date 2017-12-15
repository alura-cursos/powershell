# Usando o Get-ChildItem retornando os arquivos recursivamente conforme outras pastas são encontradas
gci -Recurse

$todosOsItens = gci -Recurse
$todosOsItens.Length

# Com o Switch argument -File nós obtemos apenas os arquivos (sem os diretórios)
$todosOsArquivos = gci -Recurse -File
$todosOsArquivos.Length

# Filtro de arquivos parecidos com "*_migrando_*" FILTER LEFT, FORMAT RIGHT
gci -recurse -file | ? Name -like "*_migrando_*" | select Name, Length


# O PowerShell oferece suporte às unidades de medida de bytes
1KB
1MB
1GB
1TB

# Podemos fazer cálculos também
654654654 / 1GB

# Usando o format operator -f
 "{0:N2}MB = {1:N2}KB" -f (1gb / 1mb), (1gb / 1kb)

# Backticks para comandos com várias linhas!
gci -recurse -file |
	? Name -like "*_migrando_*" |
	select `
		Name, `
		{ "{0:N2}KB" -f ($_.Length / 1KB) }

 