Preparação do primeiro projeto.

Criar um arquivo chamado db.properties, contendo dados do nosso SQL Workbench.

![image](https://github.com/zenonxd/jdbc/assets/64092861/7d392278-eb25-41a0-bb0c-2888db043469)


Depois, iremos criar uma classe para dar load nesse arquivo.
![image](https://github.com/zenonxd/jdbc/assets/64092861/187bacb0-05a6-402e-8037-0454507d75cd)

	1. Cria uma função que irá retornar algo do tipo Properties.
	2. Cria um laço try para leitura de arquivo. Nesse caso um FileInputStream, chamado fs, e passa db.properties. Como ele está dentro do projeto, é só escrever isso e ele irá achar o arquivo.
	3. Cria um objeto do tipo Properties chamado props e instancia.
	4. Faz o .load passando o arquivo (fs).
	5. Faz o return.

 Após isso, criaremos uma variável para instanciar a conexão: ![image](https://github.com/zenonxd/jdbc/assets/64092861/a9b495ad-5eaa-40f8-bedf-3bb49aedfeec)

 E então, criaremos uma função para conectar.
 
 ![image](https://github.com/zenonxd/jdbc/assets/64092861/df4d38f7-65ee-4f89-ae51-aaeffc0b54f0)

	1. A função getConnection, irá criar um if. Caso o conn seja nulo, ou seja, não esteja conectado a um banco de dados, entrará num laço Try.
	2. O laço try, cria uma variável props do tipo Properties, onde irá adquirir as caracteristicas da função loadProperties . Cria uma string do tipo URL, entrando no objeto props e pegando sua propriedade "dburl".
	3. Instancia uma DriveManager.getconnection. Passa a url e o props e atribui isso a conn que antes estava null.

Para finalizar, criaremos uma função para fechar a conexão.

![image](https://github.com/zenonxd/jdbc/assets/64092861/5e03e1fe-6a54-4807-9839-7d2a2deb667e)

!!Tem que passar a SQLException, assim como lá em cima. Dando o throw na DBException criada.!! 
![image](https://github.com/zenonxd/jdbc/assets/64092861/e7508dd3-dec5-49c4-8ada-443fe90dbbc2)


A classe DB serve pra ter todo o trabalho. No main para conectar no banco, é só usar isso.

![image](https://github.com/zenonxd/jdbc/assets/64092861/b81616b7-b94b-4e64-ae0c-840694af43c7)
