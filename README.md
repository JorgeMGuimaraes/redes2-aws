# Redes AWS

Demonstração do funcionamento dos métodos de segurança de rede na nuvem. 

## Apresentação

[Apresentação Online](https://gamma.app/docs/Infraestrutura-AWS-Cloud-kpn8ob0f367zrbe?mode=doc)

No link acima pode se encontrar a apresentação feita para e demonstração, com conceitos básicos de elementos de infraestrututra de redes, assom como uma representação da arquitetura final.

## Como utilizar?

> * É necessária uma conta na AWS, acesso ao Console Web e privilégios para criação de recursos. Se sua conta possui privilégios de admin, não terá problemas.
> * Estas stacks não criarão recursos computacionais, como EC2 ou Fargates, ou ainda, disponibilizar algum tipo de aplicação para testes. Você pode criar qualquer aplicação que se utilize inicialmente da porta 443, ou editar o template de security para incuir suas portas. 
> * Nada que será criado nestas stacks consome recursos (custa dinheiro). Porém, os recursos computacionais que rodarão nessa infra sim. Não esqueça de desligá-los após os testes.

- **1**: Baixe os arquivos YAML deste repositório para a sua máquina.

- **2**: Faça o Upload do Template para o S3 (opcional). 
Embora seja possível fornecer o template diretamente ao criar um stack, é recomendável fazer o upload do template para oum bucket Amazon S3 para uma melhor organização e controle de versão. Se você optar por fazer o upload para o S3, crie um bucket no S3 e faça o upload do arquivo do template para esse bucket. Por fim selecione o arquivo e copie a url dele. 

- **3**: Acesse o Console do CloudFormation. 
Faça login na AWS e acesse o Console do CloudFormation em https://console.aws.amazon.com/cloudformation/.

- **4**: Crie um novo Stack.
No console do CloudFormation, clique em "Criar novo stack" ou "Create new stack" para começar a criar um novo stack.

- **5**: Escolha um Template.
Na página "Selecione um modelo", escolha a opção adequada para especificar a localização do template. Aqui você pode inserir a url do arquivo no campo apropriado ou fazer o upload. Primeiramente suba o arquivo *network.yml*. Ele vai criar a toda a infrastrutura de rede necessária.

- **6**: Configure o Stack.
Forneça um nome para o stack e defina os parâmetros exigidos pelo seu template. Use valores de CIDR blocks válidos, como 192.x, 10.x ou 172.x. Recomendamos seguirem os valores padrão oferecidos. Se você não especificar um valor para um parâmetro, será usado o valor padrão definido no template.

- **7**: Configure as opções do Stack (opcional).
Nesta etapa, você pode configurar opções adicionais, como tags, notificações de eventos, recursos de IAM, etc. Essas opções são configuráveis de acordo com suas necessidades. Se não sabe o que fazer, não é necessário fazer nada.

- **8**: Revisar e criar o Stack.
Revise todas as configurações e opções selecionadas. Se tudo estiver correto, clique em "Criar stack" ou "Create stack" para iniciar a criação do stack. O CloudFormation começará a criar os recursos definidos no seu template.

- **9**: Aguarde a conclusão do Stack.
Aguarde até que o CloudFormation conclua a criação do stack. Você pode monitorar o progresso na página de detalhes do stack.

- **10**: Verifique o status do Stack.
Assim que o stack for criado com sucesso, você verá o status "CREATE_COMPLETE" na página de detalhes do stack. Se ocorrerem erros durante a criação do stack, você verá o status "CREATE_FAILED" e poderá analisar os registros de eventos para identificar os problemas.

- **11**: Repita os passos anteriores, porém suba o template security.yml para criar o stack de segurança. Repare que na entrada de parâmetros é necessário colocar o nome do stack de redes. Veja, não é o nome do arquivo, é sim o nome que você deu ao stack de redes. Conclua os passos e você terá criado seu stack de segurança.

- **12**: Caso seja necessário alterar os valores de IPs do stack de segurnaça, selecione-o, clique em "Atualizar", "Usar modelo atual", e em seguida altere os valores necessários. Conclua a modificação da mesma forma que a criação e aguarde a finalização.

A documentação da AWS é muito elucidativa e bem explicada, caso tenha alguma dúvida, pode consultá-la sem dificuldades.