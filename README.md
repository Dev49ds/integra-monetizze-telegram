# integra-monetizze-telegram
 O Script original, trabalha com o PostBack da Monetizze e pode ser encontrado na documentação disponível para auxiliar desenvolvedores a integrar a Monetizze às suas soluções de software
 
Script que entrega o status da compra de um produto na Monetizze para um bot de automação no Telegram.

Com base no status da compra (Aprovado ou Finalizado) e com base no número da transação, o cliente de um produto qualquer, adquirido na monetizze receberá um link de acesso, seja na página de Obigado ou por email, dizendo que ele use o número da transação como senha para acessar o produto, que no nosso caso é um grupo secreto no Telegram. Clicando no link o cliente será redirecionado para um Bot no Telegram, o qual vai pedir que o cliente entre com a a senha (o número da transação) para acessar o grupo secreto. O Bot compara o número da transação digitada pelo cliente com o número de transação registrado na tabela do DB que é chave primária e analisa os dados associados à essa chave primária. Caso o status da compra para aquele número de transação for Completa ou Finalizada, o Bot dá acesso ao grupo secreto, contrário ele exibe a mensagem "Aguardando validar transação", se a a transação já tiver sido usada, o bot exibe a mensagem: "Chave já utilizada".

Esse procedimento de validação e autenticação e feito em duas etapas, com duas linguagens sendo a primeira parte do Srcipt escrito em PHP, que processa os dados recebidos via Postback da plataforma monetizze e da segunda parte que é através do Script escrito em Python, que basicamente é o Bot que vai  receber do usuário os dados da transação, acessar os dados contidos no DB e comparar com os dados fornecidos pelo usuário, onde finalmente dá ou nega o acesso ao grupo secreto do Telegram.

Esse script está muito bem documentado e seu original pode ser baixado nesse link onde fiz o fork do código original: https://github.com/Dev49ds/ExemploPOSTCallback

