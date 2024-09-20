# resumo_lab_dio2
Resumo do segundo laboratório. SLA, criação de VM e acesso a documentação do Azure

Aprendemos sobre SLA Service Level Agreement,Acordo de Nível de Serviço 
e sua precificação e garantia de inatividade:
99       7,2 hs / mês
99,9     43,2 min / mês
99,95    21,6 min / mês
99,99    4,32 min / mês
99,999   25,9 seg / mês

Cada qual com seu custo proporcional ao Acordo 

Vimos também sobre máquinas virtuais.
   Podemos criar e hospedar uma VM no Azure
   Podemos criar e hospedar utilizando um configuração prévia
   Explorar outras soluções relacionadas a VM
	Infra estrutura híbrida
	Azure Arc VM - VM Azure Arc em ambientes não Azure
	Solução Azure VMware, máquina virtual hospedada na Azure
	Azure Arc Server - solução mais complexa que Gerencia
	servidores físicos e máquinas VM Windows e Linux hospedados
	fora do ambiente Azure
  Podemos utilizar VM Linux ou Windows

Na criação de VMs vimos que podemos utilizar uma imagem do SO da
Azure ou uma de nossa preferência.
Temos configurações pré definidas que podem nos auxiliar:
    VM de Baixo custo, VM de Alta disponibilidade ou podemos selecionar
	"Ajude-me a escolher o tamanho correto da VM"

Criação da VM:
  1. Assinatura (Os recursos são cobrados juntos em uma assinatura)
  2. Devemos definir um grupo de recursos. (Criamos AzTeste1)  
  3. Colocamos o nome da nossa VM como VM-Teste
  4. Podemos selecionar de 1 a 3 Zonas (influencia no preço) ou deixar
     o Azure escolher. Deploy para BrazilSouth(Zone) não está disponível
     O IP será compatível com a zona.
	 No nosso exemplo deixamos a Azure escolher a zona.
  5. Tipo de Segurança deixamos "Computador virtual de inicialização confiável
  6. SO escolhemos o Linux Ubuntu Serve x 64 Gen2
  7. Arquitetura de VM deixamos como padrão x64 pq não temos experiência em 
     determinar se Arm64 (RISK) seria mais indicado. Seria uma pesquisa 
	 posterior.
  8. Marcamos o Desconto de Spot do Azure com as seguintes configurações:
       Preço ou capacidade: sua máquina virtual será removida quando o excesso de 
	   capacidade do Azure desaparecer ou os custos excederem o preço máximo especificado
	   Parar/Desalocar 	
  9. Tamanho Standard_DS1_v2 - 0,00798/hora
     Preço Máximo: 0.00988  
	 
  10.Não habilitamos hibernação devido algumas restrições de uso
  11.Autenticação SSH Chave pública por ser mais seguro
  12.Usuário azureusertest, formato SSH RSA (Recomendado), nome das chave
     VM-Teste_key, permitimos portas selecionáveis e porta 22 para SSH. Como é uma simulação
     de HTTPS na porta 443.
	 
  Discos: Standard HDDs, SSD Premium, SSD V2, SSD ZRS
  Usamos imagem padrão de 60Gb, SSD com redundância local
  Disco de dados, nesse teste, como escolhemos Zona escolhida pela Azure,
  discos de dados não podem ser criados a partir de blobs ou instantâneos 
  de armazenamento
  Criptografia pela plataforma.
  Marcamos excluir Disco com a VM porque trata-se de um teste.
  
  Interface de Rede deixamos o padrão
  
  Gerenciamento básico gratuito e não habilitamos backup nesse teste

  Criamos uma regra de alerta e habilitamos diagnóstico padrão

  Não configuramos Marcas e aban

  
