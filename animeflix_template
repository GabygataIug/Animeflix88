<!DOCTYPE html>
<html>
<head>
  <title>AnimeWeb - Seu Portal de Animes</title>
  <meta name='viewport' content='width=device-width, initial-scale=1.0'/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box;}
    body {font-family: 'Roboto', sans-serif; color: #333; background-color: #f8f9fa;}
    a {text-decoration: none; color: inherit;}
    img {max-width: 100%;}
    
    /* Cabeçalho */
    header {background-color: #fff; box-shadow: 0 2px 10px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 100;}
    .header-container {max-width: 1200px; margin: 0 auto; padding: 15px 20px; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap;}
    .logo h1 {font-size: 28px; font-weight: 700;}
    .logo span {color: #8841da;}
    
    /* Busca */
    .search-container {position: relative; margin: 0 20px; flex-grow: 1; max-width: 400px;}
    .search-container input {width: 100%; padding: 10px 15px; border: 1px solid #ddd; border-radius: 30px; font-size: 14px; outline: none;}
    .search-container button {position: absolute; right: 5px; top: 50%; transform: translateY(-50%); background: none; border: none; color: #8841da; cursor: pointer; padding: 8px; font-size: 16px;}
    
    /* Navegação */
    nav ul {display: flex; list-style: none;}
    nav ul li {margin-left: 20px;}
    nav ul li a {color: #555; font-weight: 500; padding: 5px 10px; border-radius: 5px; transition: all 0.3s;}
    nav ul li a:hover, nav ul li a.active {color: #8841da; background-color: #f0e7ff;}

    /* Hero Section */
    .hero {background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://cdn.myanimelist.net/images/anime/1806/126216.jpg'); background-size: cover; background-position: center; color: white; text-align: center; padding: 100px 20px; margin-bottom: 50px;}
    .hero-content {max-width: 800px; margin: 0 auto;}
    .hero h2 {font-size: 42px; margin-bottom: 20px; text-shadow: 0 2px 5px rgba(0,0,0,0.5);}
    .hero p {font-size: 18px; margin-bottom: 30px; max-width: 600px; margin-left: auto; margin-right: auto;}
    .btn-primary {display: inline-block; background: linear-gradient(45deg, #8841da, #4e62e2); color: white; padding: 12px 30px; border-radius: 30px; font-weight: 500; box-shadow: 0 5px 15px rgba(136,65,218,0.4); transition: all 0.3s;}
    .btn-primary:hover {transform: translateY(-3px); box-shadow: 0 8px 20px rgba(136,65,218,0.6);}
    
    /* Anime Cards */
    .anime-catalog {max-width: 1200px; margin: 0 auto; padding: 0 20px 50px;}
    .section-header {display: flex; align-items: center; justify-content: space-between; margin-bottom: 30px; flex-wrap: wrap;}
    .section-header h2 {font-size: 28px; color: #333; position: relative; padding-bottom: 8px;}
    .section-header h2::after {content: ''; position: absolute; bottom: 0; left: 0; width: 50px; height: 3px; background: linear-gradient(45deg, #8841da, #4e62e2);}
    
    .filters {display: flex; gap: 10px; flex-wrap: wrap;}
    .filters select {padding: 8px 15px; border: 1px solid #ddd; border-radius: 5px; background-color: white; cursor: pointer; outline: none;}
    
    .anime-grid {display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 25px; margin-bottom: 30px;}
    .anime-card {background-color: white; border-radius: 10px; overflow: hidden; box-shadow: 0 5px 15px rgba(0,0,0,0.1); transition: transform 0.3s;}
    .anime-card:hover {transform: translateY(-5px);}
    .anime-image {position: relative; height: 280px; overflow: hidden;}
    .anime-image img {width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s;}
    .anime-card:hover .anime-image img {transform: scale(1.05);}
    .rating {position: absolute; top: 10px; right: 10px; background-color: rgba(0,0,0,0.7); color: #ffb400; padding: 3px 10px; border-radius: 20px; font-size: 12px; font-weight: 500; display: flex; align-items: center; gap: 5px;}
    .anime-overlay {position: absolute; bottom: 0; left: 0; right: 0; background: linear-gradient(transparent, rgba(0,0,0,0.8)); padding: 15px; opacity: 0; transition: opacity 0.3s; display: flex; flex-direction: column; gap: 8px;}
    .anime-card:hover .anime-overlay {opacity: 1;}
    .btn-watch, .btn-info {background-color: #8841da; color: white; padding: 6px 12px; border-radius: 5px; font-size: 12px; text-align: center; transition: background-color 0.3s;}
    .btn-info {background-color: #4e62e2;}
    .btn-watch:hover, .btn-info:hover {background-color: #6e30ba;}
    .anime-info {padding: 15px;}
    .anime-info h3 {font-size: 16px; margin-bottom: 8px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;}
    .anime-meta {display: flex; justify-content: space-between; font-size: 12px; color: #777;}

    .pagination {display: flex; justify-content: center; gap: 5px; margin-top: 40px;}
    .pagination a {display: flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 50%; border: 1px solid #ddd; color: #555; transition: all 0.3s;}
    .pagination a.active {background-color: #8841da; color: white; border-color: #8841da;}
    .pagination a:hover:not(.active) {background-color: #f0e7ff; color: #8841da;}
    
    /* Gêneros */
    .featured-genres {max-width: 1200px; margin: 0 auto; padding: 50px 20px;}
    .genre-cards {display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 20px; margin-top: 30px;}
    .genre-card {height: 200px; border-radius: 10px; overflow: hidden; position: relative; box-shadow: 0 5px 15px rgba(0,0,0,0.1); transition: transform 0.3s;}
    .genre-card:hover {transform: translateY(-5px);}
    .genre-overlay {position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(transparent, rgba(0,0,0,0.8)); display: flex; align-items: flex-end; padding: 20px;}
    .genre-overlay h3 {color: white; font-size: 24px; font-weight: 600; text-shadow: 0 2px 5px rgba(0,0,0,0.5);}

    /* Footer */
    footer {background-color: #222; color: white; padding-top: 60px;}
    .footer-container {max-width: 1200px; margin: 0 auto; padding: 0 20px 40px; display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 40px;}
    .footer-logo h2 {font-size: 28px; margin-bottom: 10px;}
    .footer-logo span {color: #8841da;}
    .footer-logo p {color: #aaa; font-size: 14px;}
    .footer-links {display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 20px;}
    .footer-section h3 {font-size: 18px; margin-bottom: 15px; color: #fff; position: relative; padding-bottom: 8px;}
    .footer-section h3::after {content: ''; position: absolute; bottom: 0; left: 0; width: 30px; height: 2px; background: #8841da;}
    .footer-section ul {list-style: none;}
    .footer-section ul li {margin-bottom: 8px;}
    .footer-section ul li a {color: #aaa; transition: color 0.3s;}
    .footer-section ul li a:hover {color: #8841da;}
    .social-icons {display: flex; gap: 15px; margin-top: 15px;}
    .social-icons a {display: flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 50%; background-color: #333; color: white; transition: all 0.3s;}
    .social-icons a:hover {background-color: #8841da; transform: translateY(-3px);}
    .footer-bottom {background-color: #1a1a1a; padding: 20px 0; text-align: center;}
    .footer-bottom p {color: #777; font-size: 14px; margin-bottom: 5px;}
    
    /* Responsividade */
    @media (max-width: 768px) {
      .header-container {flex-direction: column; align-items: flex-start;}
      .logo {margin-bottom: 15px;}
      .search-container {width: 100%; margin: 0 0 15px 0; max-width: none;}
      nav ul {width: 100%; justify-content: space-between;}
      nav ul li {margin-left: 0;}
      .hero {padding: 70px 20px;}
      .hero h2 {font-size: 32px;}
      .section-header {flex-direction: column; align-items: flex-start;}
      .section-header h2 {margin-bottom: 15px;}
      .filters {width: 100%; justify-content: space-between;}
      .filters select {flex: 1;}
      .genre-card {height: 150px;}
      .footer-container {grid-template-columns: 1fr;}
      .footer-links {grid-template-columns: 1fr 1fr;}
    }
    
    @media (max-width: 480px) {
      .anime-grid {grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: 15px;}
      .anime-image {height: 200px;}
      .footer-links {grid-template-columns: 1fr;}
    }
  </style>
</head>
<body>
  <header>
    <div class="header-container">
      <div class="logo">
        <h1>Anime<span>Web</span></h1>
      </div>
      <div class="search-container">
        <input type="text" id="search-input" placeholder="Buscar anime...">
        <button id="search-button"><i class="fas fa-search"></i></button>
      </div>
      <nav>
        <ul>
          <li><a href="#" class="active">Início</a></li>
          <li><a href="#">Populares</a></li>
          <li><a href="#">Lançamentos</a></li>
          <li><a href="#">Gêneros</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="hero-content">
        <h2>Descubra o Melhor do Mundo dos Animes</h2>
        <p>Acesse nossa coleção com milhares de animes disponíveis para assistir online</p>
        <a href="#catalog" class="btn-primary">Explorar Catálogo</a>
      </div>
    </section>

    <section id="catalog" class="anime-catalog">
      <div class="section-header">
        <h2>Catálogo de Animes</h2>
        <div class="filters">
          <select id="filter-type">
            <option value="all">Todos os tipos</option>
            <option value="TV">TV</option>
            <option value="Movie">Filme</option>
            <option value="OVA">OVA</option>
          </select>
          <select id="filter-genre">
            <option value="all">Todos os gêneros</option>
            <option value="action">Ação</option>
            <option value="comedy">Comédia</option>
            <option value="drama">Drama</option>
            <option value="fantasy">Fantasia</option>
          </select>
          <select id="filter-sort">
            <option value="popularity">Popularidade</option>
            <option value="score">Nota</option>
            <option value="newest">Mais recentes</option>
          </select>
        </div>
      </div>
      
      <div class="anime-grid">
        <!-- Anime Card 1 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/5/87048.jpg" alt="Demon Slayer">
            <div class="rating"><i class="fas fa-star"></i> 8.5</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>Demon Slayer</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">26 eps</span>
            </div>
          </div>
        </div>

        <!-- Anime Card 2 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/1208/94745.jpg" alt="Attack on Titan">
            <div class="rating"><i class="fas fa-star"></i> 9.0</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>Attack on Titan</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">25 eps</span>
            </div>
          </div>
        </div>
        
        <!-- Anime Card 3 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/10/47347.jpg" alt="Death Note">
            <div class="rating"><i class="fas fa-star"></i> 8.6</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>Death Note</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">37 eps</span>
            </div>
          </div>
        </div>
        
        <!-- Anime Card 4 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/13/17405.jpg" alt="Naruto Shippuden">
            <div class="rating"><i class="fas fa-star"></i> 8.2</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>Naruto Shippuden</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">500 eps</span>
            </div>
          </div>
        </div>

        <!-- Anime Card 5 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/6/73245.jpg" alt="One Piece">
            <div class="rating"><i class="fas fa-star"></i> 8.7</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>One Piece</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">1000+ eps</span>
            </div>
          </div>
        </div>

        <!-- Anime Card 6 -->
        <div class="anime-card">
          <div class="anime-image">
            <img src="https://cdn.myanimelist.net/images/anime/1286/99889.jpg" alt="My Hero Academia">
            <div class="rating"><i class="fas fa-star"></i> 8.3</div>
            <div class="anime-overlay">
              <a href="#" class="btn-watch">Assistir</a>
              <a href="#" class="btn-info">Mais Informações</a>
            </div>
          </div>
          <div class="anime-info">
            <h3>My Hero Academia</h3>
            <div class="anime-meta">
              <span class="type">TV</span>
              <span class="episodes">113 eps</span>
            </div>
          </div>
        </div>
      </div>

      <div class="pagination">
        <a href="#" class="page-prev"><i class="fas fa-chevron-left"></i></a>
        <a href="#" class="page active">1</a>
        <a href="#" class="page">2</a>
        <a href="#" class="page">3</a>
        <a href="#" class="page">4</a>
        <a href="#" class="page">5</a>
        <a href="#" class="page-next"><i class="fas fa-chevron-right"></i></a>
      </div>
    </section>

    <section class="featured-genres">
      <div class="section-header">
        <h2>Gêneros Populares</h2>
      </div>
      <div class="genre-cards">
        <a href="#" class="genre-card" style="background-image: url('https://cdn.myanimelist.net/images/anime/5/87048.jpg')">
          <div class="genre-overlay">
            <h3>Ação</h3>
          </div>
        </a>
        <a href="#" class="genre-card" style="background-image: url('https://cdn.myanimelist.net/images/anime/1935/127974.jpg')">
          <div class="genre-overlay">
            <h3>Aventura</h3>
          </div>
        </a>
        <a href="#" class="genre-card" style="background-image: url('https://cdn.myanimelist.net/images/anime/13/33465.jpg')">
          <div class="genre-overlay">
            <h3>Romance</h3>
          </div>
        </a>
        <a href="#" class="genre-card" style="background-image: url('https://cdn.myanimelist.net/images/anime/5/50331.jpg')">
          <div class="genre-overlay">
            <h3>Fantasia</h3>
          </div>
        </a>
      </div>
    </section>
  </main>

  <footer>
    <div class="footer-container">
      <div class="footer-logo">
        <h2>Anime<span>Web</span></h2>
        <p>Sua fonte de animes online</p>
      </div>
      <div class="footer-links">
        <div class="footer-section">
          <h3>Navegar</h3>
          <ul>
            <li><a href="#">Início</a></li>
            <li><a href="#">Animes</a></li>
            <li><a href="#">Filmes</a></li>
            <li><a href="#">Lançamentos</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h3>Gêneros</h3>
          <ul>
            <li><a href="#">Ação</a></li>
            <li><a href="#">Comédia</a></li>
            <li><a href="#">Drama</a></li>
            <li><a href="#">Sci-Fi</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h3>Sobre</h3>
          <ul>
            <li><a href="#">Sobre nós</a></li>
            <li><a href="#">Contato</a></li>
            <li><a href="#">FAQ</a></li>
            <li><a href="#">Termos</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-social">
        <h3>Siga-nos</h3>
        <div class="social-icons">
          <a href="#"><i class="fab fa-facebook"></i></a>
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-discord"></i></a>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2025 AnimeWeb. Todos os direitos reservados.</p>
      <p>Este site não armazena nenhum conteúdo protegido por direitos autorais.</p>
    </div>
  </footer>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // Filtros
      const filterType = document.getElementById('filter-type');
      if (filterType) {
        filterType.addEventListener('change', function() {
          const animeCards = document.querySelectorAll('.anime-card');
          const selectedType = this.value;
          
          animeCards.forEach(card => {
            if (selectedType === 'all') {
              card.style.display = 'block';
            } else {
              const type = card.querySelector('.type').textContent;
              card.style.display = (type === selectedType) ? 'block' : 'none';
            }
          });
        });
      }
      
      // Paginação
      const pages = document.querySelectorAll('.pagination a.page');
      pages.forEach(page => {
        page.addEventListener('click', function(e) {
          e.preventDefault();
          pages.forEach(p => p.classList.remove('active'));
          this.classList.add('active');
        });
      });
      
      // Botões de ação
      const watchButtons = document.querySelectorAll('.btn-watch');
      watchButtons.forEach(button => {
        button.addEventListener('click', function(e) {
          e.preventDefault();
          const title = this.closest('.anime-card').querySelector('h3').textContent;
          alert(`Assistindo: ${title}`);
        });
      });
      
      const infoButtons = document.querySelectorAll('.btn-info');
      infoButtons.forEach(button => {
        button.addEventListener('click', function(e) {
          e.preventDefault();
          const title = this.closest('.anime-card').querySelector('h3').textContent;
          alert(`Informações sobre: ${title}`);
        });
      });
    });
  </script>
</body>
</html>
