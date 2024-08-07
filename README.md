# CadEcommerce

![MuaKissGIF](https://github.com/user-attachments/assets/6062db80-b97e-4eb2-b265-8f6b2d8293d0)


[CadEcommerce](#cadecommerce)

[Introdução](#introdu%C3%A7%C3%A3o)

[Descrição](#descri%C3%A7%C3%A3o)

[Funcionalidades](#funcionalidades)

[Banco de dados](#banco-de-dados)

[Tecnologias utilizadas](#tecnologias-utilizadas)

[Fontes consultadas](#fontes-consultadas)

[Autores](#autores)

## Introdução
Este Projeto foi criado para facilitar o gerenciamento de produtos, marcas e categorias. Ele foi desenvolvido como parte da disciplina de Programação Web II e visa tornar a administração de inventário mais simples e eficiente.

## Descrição
Aqui você encontrará tudo o que precisa para gerenciar seu inventário de produtos. A aplicação permite cadastrar produtos, marcas e categorias, além de exibir resumos de pedidos de forma clara e organizada.

### Cadastro de Produtos
Nesta parte do sistema, você pode adicionar novos produtos. Basta preencher um formulário com o nome, descrição, quantidade em estoque, preço, categoria e marca do produto. As categorias e marcas são carregadas automaticamente do banco de dados, facilitando o processo. Depois de preencher, os dados são enviados para o script PHP ``insere-produto.php`` que salva tudo no banco de dados.

### Cadastro de Marcas
Aqui você pode adicionar novas marcas. O processo é simples: preencha a descrição da marca no formulário e envie. O script PHP ``insere-marca.php`` cuidará do resto, salvando a nova marca no banco de dados.

### Cadastro de Categorias
Adicionar novas categorias é tão fácil quanto adicionar marcas. Basta preencher a descrição da categoria no formulário e enviar. O script PHP ``insere-categoria.php`` processa a solicitação e salva a nova categoria no banco de dados.

## Funcionalidades

### Cadastro de Produtos
- **Formulário Simples**: Insira o nome, descrição, quantidade em estoque, preço, categoria e marca do produto.
- **Banco de Dados**: Os dados são salvos na tabela `produtos` do banco de dados.
- **Visualização de Produtos**: Veja todos os produtos cadastrados em uma página resumida.

#### Exemplo de Código PHP
```php
<?php
include_once('controller/conexao.php');

$categoria = $_POST['seleciona_categoria'];
$marca = $_POST['seleciona_marca'];
$nome_produto = $_POST['nome'];
$descricao = $_POST['descricao'];
$estoque = $_POST['estoque'];
$preco = $_POST['preco'];

// Insere o novo produto no banco de dados
$grava_produto = "INSERT INTO produtos (IDCATEGORIA, IDMARCA, NOME, DESCRICAO, ESTOQUE, PRECO) VALUES ('$categoria', '$marca', '$nome_produto', '$descricao', '$estoque', '$preco')";

$resute_gravacao = mysqli_query($mysqli, $grava_produto);
if (mysqli_affected_rows($mysqli) != 0) {
    echo "
    <META HTTP-EQUIV=REFRESH CONTENT = '0;URL=produtos.php'>
    <script type=\"text/javascript\">
      alert('Produto cadastrado com sucesso');
    </script>
    ";
} else {
    echo "
    <META HTTP-EQUIV=REFRESH CONTENT = '0;URL=produto.php'>
    <script type=\"text/javascript\">
    alert('Produto não cadastrado, tente novamente');
    </script>
    ";
}
?>
```
### Explicação do Código
Este script recebe os dados do formulário de cadastro de produtos (categoria, marca, nome, descrição, estoque e preço) e insere esses dados na tabela ``produtos`` do banco de dados. Se a inserção for bem-sucedida, uma mensagem de sucesso é exibida. Caso contrário, uma mensagem de erro é mostrada.

Exemplo de Uso
Para cadastrar um novo produto, preencha os campos no formulário, selecione a categoria e a marca, e clique em "Cadastrar".

### Cadastro de Marcas
- Formulário Simples: Insira a descrição da marca.
- Banco de Dados: Os dados são salvos na tabela marca.
- Feedback Imediato: Saiba se a marca foi cadastrada com sucesso.
```
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];

// Exibe a descrição da nova marca
echo "<h3> Descrição: $descricao </h3></br>";

// Insere a nova marca no banco de dados
$cad_marca = "INSERT INTO marca(DESCRICAO) VALUES ('$descricao')";

if (mysqli_query($mysqli, $cad_marca)) {
    echo "<h1>Nova marca cadastrada com sucesso</h1></br>";
} else {
    echo "Erro: " . $cad_marca . "</br>" . mysqli_error($mysqli);
}

mysqli_close($mysqli);
?>

```
### Explicação do Código
Este script recebe a descrição da nova marca do formulário e a insere na tabela ``marca`` do banco de dados. Após a inserção, uma mensagem de sucesso ou erro é exibida.

### Exemplo de Uso
Para cadastrar uma nova marca, preencha o campo de descrição no formulário e clique em "Cadastrar".

### Cadastro de Categorias
- Formulário Simples: Insira a descrição da categoria.
- Banco de Dados: Os dados são salvos na tabela ``categoria``.
```
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];

// Exibe a descrição da nova categoria
echo "<h3> Descrição: $descricao </br>";

// Insere a nova categoria no banco de dados
$cad_categoria = "INSERT INTO categoria(DESCRICAO) VALUES ('$descricao')";

if (mysqli_query($mysqli, $cad_categoria)) {
    echo "<h1>Nova categoria cadastrada com sucesso</h1></br>";
} else {
    echo "Erro: " . $cad_categoria . "</br>" . mysqli_error($mysqli);
}

mysqli_close($mysqli);
?>

```
### Explicação do Código
Este script recebe a descrição da nova categoria do formulário e a insere na tabela ``categoria`` do banco de dados. Após a inserção, uma mensagem de sucesso ou erro é exibida.

### Exemplo de Uso
Para cadastrar uma nova categoria, preencha o campo de descrição no formulário e clique em "Cadastrar".

## Banco de Dados

![img do codigo](img3.png)
![img do codigo](img.png.png)
![img do codigo](img.2.png)

## Tecnologias Utilizadas
- ``PHP``
- ``HTML5``
- ``CSS3``
- ``MySQL``
- ``JavaScript (jQuery)``

# Fontes consultadas
- [Leonardo](https://github.com/LeonardoRochaMarista/LeonardoRochaMarista)
  
- [ChatGPT](https://chatgpt.com/)
# Autores
- [Gabriella](https://github.com/gaabriellasantoos)
- [Leonardo](https://github.com/LeonardoRochaMarista/LeonardoRochaMarista)
