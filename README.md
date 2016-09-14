# Teste para candidatos à vaga de desenvolvedor iOS
:pencil: Teste para candidatos à vaga de desenvolvedor iOS no Viva Decora

> [![Logo Viva Decora](https://cdn.rawgit.com/vivadecora/backend-teste/master/vivadecora-logo.png)](https://www.vivadecora.com.br)
>
> Esse teste é público. Candidatos para o teste devem implementar a aplicação solicitada e criar uma issue com um link para um repositório com a solução do mesmo.

## Objetivo do teste

Implementar em Objective-C um aplicativo nativo para iOS que consulte uma API e mostre uma lista de locais (com foto) e uma tela de detalhes.

### Requisitos
- Seguir as diretrizes do iOS Human Interface Guidelines
- Fazer cache das imagens
- Se não houver internet, exibir mensagem com botão para tentar novamente
- Tela responsiva
- Touch feedback

### Tela 1 (Lista de locais):

Deve ser feita uma lista, em que cada elemento tenha a imagem, o nome do local("venue"), a descrição("note") quando houver e o número de visualizações, conforme imagem abaixo:

![alt text](https://github.com/vivadecora/ios-teste/blob/master/iPhone%2001.png "Tela 1")

### Tela 2 (Detalhes do local): 

Deve ser feita uma tela de detalhes, que abre a partir do clique em um item da lista da Tela 1. Deve ser exibido a imagem, o nome ("name"), o endereço ("address", "city", "state", "country") e a média de nota ("average_rating"). Quando existir, deve mostrar o conteúdo "stats" e o "link". 

![alt text](https://github.com/vivadecora/ios-teste/blob/master/iPhone%2002.png "Tela 2")

### Objetivo Bônus:

- Utilização de bibliotecas para consumo de serviços (Ion ou Retrofit)
- Compartilhamento quanto tiver link de web (na tela de detalhes).
- Sem ocorrências de overdraw
- Sinta-se à vontade para fazer seu bônus

### API:

Essa API permite diversos tipos de consultas. Ela é baseada em fotos postadas por usuários. Eles postam fotos da visão de seus assentos em estádios, concertos e teatros. Para utilizá-la é necessário um cadastro que gera uma chave. Já fizemos o cadastro e já estamos fornecendo a chave direto na url.



#### A url para obter os dados da Tela 1 (Lista):
> https://aviewfrommyseat.com/avf/api/featured.php?appkey=f6bcd8e8bb853890f4fb2be8ce0418fa 

#### A url para obter a imagem de cada item da lista da Tela 1 é obtida concatenando a url abaixo mais o campo "image" que retorna no json: 

```
http://aviewfrommyseat.com/wallpaper/<image>
```

#### A url para obter os dados da Tela 2 (Detalhes) é obtida concatenando o nome da venue na url no lugar de "<nome da venue>:

```
https://aviewfrommyseat.com/avf/api/venue.php?appkey=f6bcd8e8bb853890f4fb2be8ce0418fa&venue=<nome da venue>&info=true
```

(Exemplo: https://aviewfrommyseat.com/avf/api/venue.php?appkey=f6bcd8e8bb853890f4fb2be8ce0418fa&venue=Arthur+Ashe+Stadium&info=true)

#### A url para obter a imagem da Tela 2 (Detalhes) é obtida concatenando a string do campo “newest_image” na url:

```
http://aviewfrommyseat.com/photos/<newest_image>
```

#### Documentação completa:

```
http://developer.aviewfrommyseat.com/docs.php#api_featured
```

#### Submissão:
Crie um repositório com o nome recrutamento-ios na sua conta do GitHub ou Bitbucket e mande a url do repositório

