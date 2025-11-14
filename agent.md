Create a modern, stylish, and visually stunning single-page web application showcasing 10 unique eggplant (ナス) dishes. The website should be built with HTML, CSS, and JavaScript and include the following features:

1. **Layout & Design**
   - Full-screen hero section with a high-quality banner image of roasted and grilled eggplants.
   - Smooth scrolling with section-based navigation (10 sections, one for each dish).
   - Minimalistic, modern design with soft gradients, shadow effects, and rounded corners.
   - Use a pastel color palette (purples, greens, soft neutrals) to highlight eggplant theme.
   - Responsive design: works perfectly on desktop, tablet, and mobile.
   - Clean typography: modern sans-serif font with readable sizes; headings bold and large.

2. **Dish Sections**
   - Each of the 10 eggplant dishes should have its own card or section including:
     - High-resolution image (use AI-generated or placeholder images first).
     - Dish name in bold, large text.
     - Short description and “why it’s delicious” tagline.
     - Hover effects: slight scale-up, shadow pop, and a subtle color glow matching the dish.
     - Optional “View Recipe” button that opens a modal or expands the recipe.

3. **Interactive Elements**
   - Smooth fade-in or slide-in animations for each section when scrolling.
   - Interactive image gallery: click dish image → fullscreen lightbox with more images.
   - Sticky top navigation with dish thumbnails that highlight as you scroll.
   - Subtle parallax effect on hero banner for depth.

4. **JavaScript Features**
   - Automatic scroll snapping between dish sections.
   - Filter or search functionality: user can type or select “Grilled, Baked, Fried” etc.
   - Animated counters for “Total Dishes”, “Recipes Available”, etc. (optional decorative element).
   - Modal pop-ups for recipe details with collapsible ingredients & instructions.

5. **Visual & UX Details**
   - Micro-interactions: hover animations on buttons and dish cards.
   - Light & dark mode toggle with smooth transition.
   - Include icons or illustrations for ingredients (like garlic, cheese, tomato) next to recipe.
   - Subtle background animation: floating vegetable icons or gradient waves for ambiance.

6. **Overall Mood**
   - High-end foodie / Instagram-worthy aesthetic.
   - Clean, airy, modern look with attention to spacing and alignment.
   - Professional portfolio feel but playful and appetizing.
   - Ensure the site instantly communicates “these dishes are delicious and trendy”.

**Deliverables:**
- HTML structure with semantic tags.
- CSS styling with modern layout (flex/grid), gradients, shadows, animations.
- JavaScript for interactive scrolling, modals, filtering, and lightbox functionality.
- Fully responsive, mobile-first design.
- Ready for AI image integration for each dish section.

Include comments in code explaining where to replace images, text, and recipes for each of the 10 eggplant dishes.


<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Eggplant Delights - ナス料理ギャラリー</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
<style>
  /* Reset */
  * { margin:0; padding:0; box-sizing:border-box; font-family:'Montserrat', sans-serif; }

  body { background: #fafafa; color: #333; }
  h1,h2,h3 { font-weight:700; }

  /* Hero Section */
  .hero {
    height: 80vh;
    background: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('https://images.unsplash.com/photo-1617196030113-fb2c31a1f1b6?auto=format&fit=crop&w=1950&q=80') center/cover no-repeat;
    display: flex; justify-content: center; align-items: center;
    color: #fff; text-align: center;
  }
  .hero h1 { font-size:3rem; text-shadow: 2px 2px 8px rgba(0,0,0,0.5); }

  /* Navigation */
  nav {
    position: sticky; top:0; background:#fff; padding:1rem 2rem; display:flex; justify-content:center; gap:1rem; z-index:100;
    box-shadow:0 2px 6px rgba(0,0,0,0.1);
  }
  nav a { text-decoration:none; color:#555; font-weight:600; transition:0.3s; }
  nav a.active, nav a:hover { color:#8B3E99; }

  /* Dish Sections */
  .dish-section { padding:4rem 2rem; display:flex; flex-wrap:wrap; justify-content:center; gap:2rem; opacity:0; transform:translateY(30px); transition: all 0.6s ease-in-out; }
  .dish-card {
    background:#fff; border-radius:16px; box-shadow:0 4px 15px rgba(0,0,0,0.1); overflow:hidden;
    width:300px; cursor:pointer; transition: transform 0.3s, box-shadow 0.3s;
  }
  .dish-card:hover { transform:scale(1.05); box-shadow:0 10px 25px rgba(0,0,0,0.2); }
  .dish-card img { width:100%; height:200px; object-fit:cover; }
  .dish-card .content { padding:1rem; }
  .dish-card h3 { margin-bottom:0.5rem; color:#8B3E99; }
  .dish-card p { font-size:0.9rem; color:#555; }

  /* Modal */
  .modal { position:fixed; top:0; left:0; width:100%; height:100%; background: rgba(0,0,0,0.7); display:none; justify-content:center; align-items:center; z-index:200; }
  .modal-content { background:#fff; border-radius:12px; padding:2rem; max-width:600px; width:90%; position:relative; }
  .close { position:absolute; top:1rem; right:1rem; font-size:1.5rem; cursor:pointer; color:#8B3E99; }

  /* Responsive */
  @media (max-width:768px) { .dish-card { width:90%; } }
</style>
</head>
<body>

<!-- Hero -->
<section class="hero">
  <h1>Eggplant Delights - ナス料理ギャラリー</h1>
</section>

<!-- Navigation -->
<nav>
  <a href="#dish1">ガーリックバター</a>
  <a href="#dish2">ラザニア</a>
  <a href="#dish3">照り焼きステーキ</a>
  <a href="#dish4">カプレーゼ</a>
  <a href="#dish5">キーマカレー</a>
  <a href="#dish6">カポナータ</a>
  <a href="#dish7">ハニーチーズ</a>
  <a href="#dish8">麻婆</a>
  <a href="#dish9">ミートボールサブ</a>
  <a href="#dish10">クリスピーフライ</a>
</nav>

<!-- Dish Sections -->
<section id="dish1" class="dish-section">
  <div class="dish-card" data-recipe="ナスを縦半分に切り込み、ガーリックバターを塗りオーブン200℃で15分焼く">
    <img src="https://images.unsplash.com/photo-1617196030113-fb2c31a1f1b6?auto=format&fit=crop&w=800&q=80" alt="ガーリックバターナス">
    <div class="content">
      <h3>とろけるガーリックバターグリル</h3>
      <p>ジューシーなナスにガーリックバターの香りがたまらない一品。</p>
    </div>
  </div>
</section>

<section id="dish2" class="dish-section">
  <div class="dish-card" data-recipe="薄切りナスを焼き、ミートソースとチーズでラザニアの層にして180℃で20分焼く">
    <img src="https://images.unsplash.com/photo-1627308595229-7830a5c91f9f?auto=format&fit=crop&w=800&q=80" alt="ナスラザニア">
    <div class="content">
      <h3>ナスのラザニア</h3>
      <p>ナスでグルテンフリーのラザニア。とろけるチーズとソースが絶品。</p>
    </div>
  </div>
</section>

<section id="dish3" class="dish-section">
  <div class="dish-card" data-recipe="分厚く切ったナスを焼き、照り焼きソースで絡める">
    <img src="https://images.unsplash.com/photo-1617196042117-19ef6d6d3a6f?auto=format&fit=crop&w=800&q=80" alt="ナス照り焼き">
    <div class="content">
      <h3>ナスの照り焼きステーキ</h3>
      <p>肉のような食感に照り焼きソースが絡む、老若男女に人気の味。</p>
    </div>
  </div>
</section>

<section id="dish4" class="dish-section">
  <div class="dish-card" data-recipe="揚げ焼きナスとトマト、モッツァレラ、バジルでカプレーゼに">
    <img src="https://images.unsplash.com/photo-1627319440232-1e05723d2f7a?auto=format&fit=crop&w=800&q=80" alt="ナスカプレーゼ">
    <div class="content">
      <h3>ナスとモッツァレラのカプレーゼ</h3>
      <p>色鮮やかでヘルシー、見た目も味も楽しめる一皿。</p>
    </div>
  </div>
</section>

<section id="dish5" class="dish-section">
  <div class="dish-card" data-recipe="角切りナスを炒め、マイルドなミートベースのカレーで煮込む">
    <img src="https://images.unsplash.com/photo-1604908177521-4dba5b9b66be?auto=format&fit=crop&w=800&q=80" alt="ナスキーマカレー">
    <div class="content">
      <h3>ナスのマイルドキーマカレー</h3>
      <p>ナスがカレーソースを吸い込んでジューシー、辛さ控えめで誰でも楽しめる。</p>
    </div>
  </div>
</section>

<section id="dish6" class="dish-section">
  <div class="dish-card" data-recipe="ナス、玉ねぎ、セロリ、トマトをオリーブオイルで煮て甘酸っぱく仕上げる">
    <img src="https://images.unsplash.com/photo-1606312619116-0b4b9d9ecb3f?auto=format&fit=crop&w=800&q=80" alt="ナスカポナータ">
    <div class="content">
      <h3>ナスのカポナータ</h3>
      <p>地中海風の甘酸っぱい野菜煮で、パンやパスタにぴったり。</p>
    </div>
  </div>
</section>

<section id="dish7" class="dish-section">
  <div class="dish-card" data-recipe="ナスを焼き、蜂蜜とクリームチーズをのせ、オーブンで少し焼く">
    <img src="https://images.unsplash.com/photo-1617196029854-d5a3eabe5f13?auto=format&fit=crop&w=800&q=80" alt="ナスハニーチーズ">
    <div class="content">
      <h3>ナスのハニーチーズロースト</h3>
      <p>甘じょっぱい組み合わせがクセになる、見た目も華やか。</p>
    </div>
  </div>
</section>

<section id="dish8" class="dish-section">
  <div class="dish-card" data-recipe="ナスを炒め、味噌と甜麺醤でとろみをつけたマイルド麻婆ナス">
    <img src="https://images.unsplash.com/photo-1606851093137-bd52c1a0c6fa?auto=format&fit=crop&w=800&q=80" alt="ナス麻婆">
    <div class="content">
      <h3>ナスのマイルド麻婆</h3>
      <p>辛さ控えめ、子どもや海外の方にも食べやすい中華料理。</p>
    </div>
  </div>
</section>

<section id="dish9" class="dish-section">
  <div class="dish-card" data-recipe="細かく刻んだナスをミートボールに混ぜ、トマトソースとチーズで焼くサンド">
    <img src="https://images.unsplash.com/photo-1627308611272-8460b8b1637b?auto=format&fit=crop&w=800&q=80" alt="ナスミートボールサブ">
    <div class="content">
      <h3>ナス入りミートボールサブ</h3>
      <p>ジューシーでヘルシーなミートボールをバゲットにサンド。</p>
    </div>
  </div>
</section>

<section id="dish10" class="dish-section">
  <div class="dish-card" data-recipe="薄切りナスをカリッと揚げ、塩・ガーリックパウダーで味付け">
    <img src="https://images.unsplash.com/photo-1617196051021-8f2e4b7d7c22?auto=format&fit=crop&w=800&q=80" alt="ナスクリスピーフライ">
    <div class="content">
      <h3>ナスのクリスピーフライ</h3>
      <p>カリカリ食感のナスチップ、ディップと合わせて楽しめるスナック。</p>
    </div>
  </div>
</section>

<!-- Modal -->
<div class="modal" id="recipeModal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2 id="modalTitle"></h2>
    <p id="modalRecipe"></p>
  </div>
</div>

<script>
  // Scroll fade-in animation
  const sections = document.querySelectorAll('.dish-section');
  window.addEventListener('scroll', () => {
    const triggerBottom = window.innerHeight / 5 * 4;
    sections.forEach(section => {
      const sectionTop = section.getBoundingClientRect().top;
      if(sectionTop < triggerBottom) {
        section.style.opacity = 1;
        section.style.transform = 'translateY(0)';
      }
    });
  });

  // Modal logic
  const modal = document.getElementById('recipeModal');
  const modalTitle = document.getElementById('modalTitle');
  const modalRecipe = document.getElementById('modalRecipe');
  const closeBtn = document.querySelector('.close');
  document.querySelectorAll('.dish-card').forEach(card => {
    card.addEventListener('click', () => {
      modal.style.display = 'flex';
      modalTitle.innerText = card.querySelector('h3').innerText;
      modalRecipe.innerText = card.dataset.recipe;
    });
  });
  closeBtn.addEventListener('click', ()=> modal.style.display='none');
  window.addEventListener('click', e => { if(e.target === modal) modal.style.display='none'; });

  // Navigation active state
  const navLinks = document.querySelectorAll('nav a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach((section, idx) => {
      const sectionTop = section.offsetTop - 150;
      if(scrollY >= sectionTop) { current = `dish${idx+1}`; }
    });
    navLinks.forEach(link => { link.classList.remove('active'); if(link.getAttribute('href') === `#${current}`) link.classList.add('active'); });
  });
</script>

</body>
</html>
