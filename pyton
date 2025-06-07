import zipfile

# Conteúdo dos arquivos
files = {
    "index.html": """<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mato Seco Tabacaria</title>
  <link rel="stylesheet" href="style.css" />
  <script defer src="script.js"></script>
</head>
<body>
  <header>
    <h1>Mato Seco Tabacaria</h1>
    <nav>
      <ul>
        <li><a href="#home">Início</a></li>
        <li><a href="#produtos">Produtos</a></li>
        <li><a href="#sobre">Sobre</a></li>
        <li><a href="#contato">Contato</a></li>
      </ul>
    </nav>
  </header>

  <section id="home" class="banner">
    <h2>Bem-vindo à Mato Seco Tabacaria</h2>
    <p>Seu destino para os melhores produtos de tabacaria</p>
  </section>

  <section id="produtos" class="produtos">
    <h2>Nossos Produtos</h2>
    <div class="grid">
      <div class="produto">
        <img src="https://via.placeholder.com/200x200" alt="Produto 1" />
        <h3>Seda Premium</h3>
        <p>R$ 10,00</p>
        <button onclick="adicionarCarrinho('Seda Premium', 10)">Adicionar ao Carrinho</button>
      </div>
      <div class="produto">
        <img src="https://via.placeholder.com/200x200" alt="Produto 2" />
        <h3>Piteira de Vidro</h3>
        <p>R$ 25,00</p>
        <button onclick="adicionarCarrinho('Piteira de Vidro', 25)">Adicionar ao Carrinho</button>
      </div>
      <div class="produto">
        <img src="https://via.placeholder.com/200x200" alt="Produto 3" />
        <h3>Essência de Menta</h3>
        <p>R$ 15,00</p>
        <button onclick="adicionarCarrinho('Essência de Menta', 15)">Adicionar ao Carrinho</button>
      </div>
    </div>
  </section>

  <section id="sobre" class="sobre">
    <h2>Sobre Nós</h2>
    <p>A Mato Seco Tabacaria é especializada em produtos de alta qualidade para quem valoriza uma boa sessão.</p>
  </section>

  <section id="contato" class="contato">
    <h2>Contato</h2>
    <p>Email: contato@matosecotabacaria.com.br</p>
    <p>Instagram: @matosecotabacaria</p>
    <p><a href="https://wa.me/5599999999999" target="_blank">Fale conosco no WhatsApp</a></p>
  </section>

  <section class="carrinho">
    <h2>Carrinho de Compras</h2>
    <ul id="itens-carrinho"></ul>
    <p>Total: R$ <span id="total">0.00</span></p>
  </section>

  <footer>
    <p>&copy; 2025 Mato Seco Tabacaria. Todos os direitos reservados.</p>
  </footer>
</body>
</html>
""",
    "style.css": """
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f8f3ec;
  color: #2c2c2c;
}

header {
  background-color: #3e2f1c;
  color: #fff;
  padding: 20px;
  text-align: center;
}

nav ul {
  list-style: none;
  display: flex;
  justify-content: center;
  padding: 0;
}

nav ul li {
  margin: 0 15px;
}

nav ul li a {
  color: #fff;
  text-decoration: none;
}

.banner {
  background-image: url('https://via.placeholder.com/1200x400?text=Mato+Seco+Tabacaria');
  background-size: cover;
  color: #fff;
  text-align: center;
  padding: 100px 20px;
}

.produtos {
  padding: 40px 20px;
  text-align: center;
}

.grid {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

.produto {
  background-color: #fff;
  border: 1px solid #ddd;
  padding: 15px;
  width: 200px;
  border-radius: 8px;
}

.produto img {
  width: 100%;
  border-radius: 4px;
}

.sobre, .contato, .carrinho {
  padding: 40px 20px;
  text-align: center;
}

footer {
  background-color: #3e2f1c;
  color: #fff;
  text-align: center;
  padding: 20px;
}
""",
    "script.js": """
let carrinho = [];
let total = 0;

function adicionarCarrinho(produto, preco) {
  carrinho.push({ produto, preco });
  total += preco;
  atualizarCarrinho();
}

function atualizarCarrinho() {
  const lista = document.getElementById('itens-carrinho');
  const totalSpan = document.getElementById('total');
  lista.innerHTML = '';
  carrinho.forEach(item => {
    const li = document.createElement('li');
    li.textContent = `${item.produto} - R$ ${item.preco.toFixed(2)}`;
    lista.appendChild(li);
  });
  totalSpan.textContent = total.toFixed(2);
}
"""
}

# Criar o zip
with zipfile.ZipFile("matoseco_tabacaria_site.zip", "w") as zipf:
    for filename, content in files.items():
        zipf.writestr(filename, content)

print("Arquivo ZIP criado com sucesso!")
