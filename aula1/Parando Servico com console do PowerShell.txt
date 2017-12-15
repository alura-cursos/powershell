# Comando para obtermos o serviço no computador da rede chamado SRV01
# DICA: Para obtermos um serviço em nossa máquina local, podemos omitir o argumento -ComputerName
Get-Service -Name "ByteBank Interface Service" -ComputerName "SRV01"

# Armazenando o resultado do comando em uma variável
$servico = Get-Service -Name "ByteBank Interface Service" -ComputerName "SRV01"

# Invocando métodos deste objeto
$servico.Stop()
$servico.Start()