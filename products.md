---
layout: default
title: محصولات
permalink: /products/
---

<div class="products-page">
  <div class="container">
    <div class="page-header">
      <h1>محصولات نینی‌نیت</h1>
      <p>مجموعه‌ای از زیباترین لباس‌های بافتنی دست‌ساز برای نوزادان و کودکان</p>
    </div>

    <!-- Categories Navigation -->
    <div class="categories-nav">
      <h2>دسته‌بندی محصولات</h2>
      <div class="categories-grid">
        {% for category in site.categories %}
          <a href="{{ category.url }}" class="category-card">
            <div class="category-icon">
              {% if category.slug == 'sweaters' %}🧥
              {% elsif category.slug == 'hats' %}🧢
              {% elsif category.slug == 'booties' %}🧦
              {% elsif category.slug == 'sets' %}👶
              {% else %}🛍️
              {% endif %}
            </div>
            <h3>{{ category.title }}</h3>
            <p>{{ category.description }}</p>
            <span class="category-count">
              {% assign category_products = site.products | where: 'category', category.slug %}
              {{ category_products.size }} محصول
            </span>
          </a>
        {% endfor %}
      </div>
    </div>

    <!-- Featured Products -->
    <div class="featured-products">
      <h2>محصولات ویژه</h2>
      <div class="products-grid">
        {% for product in site.products limit: 6 %}
          <div class="product-card">
            <div class="product-image">
              {% if product.images %}
                <img src="{{ product.images[0] | relative_url }}" alt="{{ product.title }}" onerror="this.style.display='none'">
              {% else %}
                <div class="placeholder-image">
                  <span class="placeholder-icon">🖼️</span>
                </div>
              {% endif %}
              <div class="product-overlay">
                <a href="{{ product.url }}" class="btn btn-primary">مشاهده جزئیات</a>
              </div>
            </div>
            <div class="product-info">
              <h3>{{ product.title }}</h3>
              <p>{{ product.description }}</p>
              {% if product.price %}
                <div class="product-price">{{ product.price }} تومان</div>
              {% endif %}
              <div class="product-actions">
                <a href="{{ product.url }}" class="btn btn-outline">مشاهده</a>
                <a href="https://wa.me/989171035286?text=سلام، در مورد {{ product.title }} سوال دارم" class="btn btn-whatsapp" target="_blank">سوال دارم</a>
              </div>
            </div>
          </div>
        {% endfor %}
      </div>
    </div>

    <div class="custom-order-section">
      <h2>سفارش خاص</h2>
      <p>آیا محصول مورد نظرتان را در اینجا پیدا نکردید؟ ما آماده‌ایم تا طبق درخواست شما محصولات سفارشی ببافیم.</p>
      <a href="https://wa.me/989171035286?text=سلام، می‌خواهم سفارش خاصی بدهم" class="btn btn-primary">سفارش خاص</a>
    </div>

    <div class="contact-info">
      <h2>راه‌های ارتباط با ما</h2>
      <div class="contact-methods">
        <a href="https://wa.me/989171035286" class="contact-method">
          <span class="contact-icon">📱</span>
          <div>
            <h3>واتساپ</h3>
            <p>برای سفارش و مشاوره</p>
          </div>
        </a>
        <a href="https://instagram.com/niniknit_azar" class="contact-method">
          <span class="contact-icon">📷</span>
          <div>
            <h3>اینستاگرام</h3>
            <p>مشاهده آخرین محصولات</p>
          </div>
        </a>
      </div>
    </div>
  </div>
</div>

<style>
.categories-nav {
  margin-bottom: 60px;
}

.categories-nav h2 {
  text-align: center;
  margin-bottom: 40px;
  color: #2c3e50;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  margin-bottom: 40px;
}

.category-card {
  background: white;
  padding: 30px 20px;
  border-radius: 15px;
  text-align: center;
  text-decoration: none;
  color: inherit;
  box-shadow: 0 5px 15px rgba(0,0,0,0.08);
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.category-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
  border-color: #667eea;
  text-decoration: none;
  color: inherit;
}

.category-icon {
  font-size: 3rem;
  margin-bottom: 15px;
}

.category-card h3 {
  color: #2c3e50;
  margin-bottom: 10px;
  font-size: 1.3rem;
}

.category-card p {
  color: #666;
  margin-bottom: 15px;
  line-height: 1.6;
}

.category-count {
  background: #f8f9fa;
  color: #667eea;
  padding: 5px 15px;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
}

.featured-products {
  margin-bottom: 60px;
}

.featured-products h2 {
  text-align: center;
  margin-bottom: 40px;
  color: #2c3e50;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.product-card {
  background: white;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
}

.product-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.product-card:hover .product-image img {
  transform: scale(1.05);
}

.placeholder-image {
  width: 100%;
  height: 100%;
  background: #f8f9fa;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #666;
}

.placeholder-icon {
  font-size: 3rem;
}

.product-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0,0,0,0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.product-card:hover .product-overlay {
  opacity: 1;
}

.product-info {
  padding: 20px;
}

.product-info h3 {
  color: #2c3e50;
  margin-bottom: 10px;
  font-size: 1.3rem;
}

.product-info p {
  color: #666;
  margin-bottom: 15px;
  line-height: 1.6;
}

.product-price {
  color: #667eea;
  font-weight: 700;
  font-size: 1.1rem;
  margin-bottom: 15px;
}

.product-actions {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.product-actions .btn {
  flex: 1;
  text-align: center;
  font-size: 0.9rem;
  padding: 8px 16px;
}

@media (max-width: 768px) {
  .categories-grid {
    grid-template-columns: 1fr;
  }
  
  .products-grid {
    grid-template-columns: 1fr;
  }
  
  .product-actions {
    flex-direction: column;
  }
  
  .product-actions .btn {
    width: 100%;
  }
}
</style>