<template>
  <header class="header" id="header">
    <div class="header__toggle">
      <i class='bx bx-menu' id="header-toggle"></i>
    </div>

    <div class="header__img">
      <img src="../assets/img/perfil.jpg" alt="">
    </div>
  </header>

  <!-- Barra lateral-->

  <div class="sidebar " id="nav-bar">
    <div class="logo-details">
      <i class="fa-solid fa-shield-dog icon"></i>
      <div class="logo_name">PETSHOP</div>
    </div>
    <ul class="nav-list">
      <hr>
      <li>
        <a href="#">
          <router-link to="/">
            <i class="fa-solid fa-calendar-days"></i>
            <span class="links_name">Agenda</span>
          </router-link>
        </a>
        <span class="tooltip">Agenda</span>
      </li>
      <li>
        <a href="#">
          <router-link to="/caixa">
            <i class="fa-solid fa-basket-shopping"></i>
            <span class="links_name">Caixa</span>
          </router-link>
        </a>
        <span class="tooltip">Caixa</span>
      </li>
      <li>
        <a href="#">
          <router-link to="/clientes">
            <i class="fa-solid fa-users"></i>
            <span class="links_name">Clientes</span>
          </router-link>
        </a>
        <span class="tooltip">Clientes</span>
      </li>
      <li>
        <a href="#">
          <router-link to="/pets">
            <i class="fa-solid fa-dog"></i>
            <span class="links_name">Pets</span>
          </router-link>
        </a>
        <span class="tooltip">Pets</span>
      </li>
      <li>
        <a href="#">
          <router-link to="/estoque">
            <i class="fa-solid fa-box"></i>
            <span class="links_name">Estoque</span>
          </router-link>
        </a>
        <span class="tooltip">Estoque</span>
      </li>
      <hr>
      <li>
        <a href="#">
          <router-link to="/config">
            <i class="fa-solid fa-gear"></i>
            <span class="links_name">Configurações</span>
          </router-link>
        </a>
        <span class="tooltip">Configurações</span>
      </li>
      <li class="profile">
        <a href="#">
          <i class='bx bx-log-out' id="log_out"></i>
          <span class="links_name">Sair</span>
        </a>
        <span class="tooltip">Sair</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Nav',
}


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');

/*===== VARIABLES CSS =====*/
:root {
  --header-height: 3rem;
  --nav-width: 70px;

  /*===== Colors =====*/
  --first-color: #3C58A6;
  --first-color-light: #AFA5D9;
  --white-color: #F7F6FB;

  /*===== Font and typography =====*/
  --body-font: 'Nunito', sans-serif;
  --normal-font-size: 1rem;

  /*===== z index =====*/
  --z-fixed: 100;
}

/*===== BASE =====*/
*,
::before,
::after {
  box-sizing: border-box;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  position: relative;
  margin: var(--header-height) 0 0 0;
  padding: 0 1rem;
  font-family: var(--body-font);
  font-size: var(--normal-font-size);
  transition: .5s;
  background-color: #8b8b8b4b;
}

a {
  text-decoration: none;
}

/*===== HEADER =====*/
.header {
  width: 100%;
  height: var(--header-height);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 1rem;
  background-color: var(--white-color);
  z-index: var(--z-fixed);
  transition: .5s;
  position: fixed;
}

.header__toggle {
  color: var(--first-color);
  font-size: 1.5rem;
  cursor: pointer;
}

.header__img {
  width: 35px;
  height: 35px;
  display: flex;
  justify-content: center;
  border-radius: 50%;
  overflow: hidden;
}

.header__img img {
  width: 40px;
}

/*===== NAV =====*/
.sidebar {
  position: fixed;
  left: 0;
  top: 0;
  height: 100%;
  width: 78px;
  background: #3C58A6;
  padding: 6px 14px;
  z-index: 101;
  transition: all 0.5s ease;
}

.sidebar .logo-details {
  height: 60px;
  display: flex;
  align-items: center;
  position: relative;
}

.sidebar .logo-details .icon {
  opacity: 1;
  transition: all 0.5s ease;
}

.sidebar .logo-details .logo_name {
  color: #fff;
  font-size: 20px;
  font-weight: 600;
  opacity: 1;
  transition: all 0.5s ease;
  margin-left: 15px;
  overflow: hidden;
}

.sidebar.open .logo-details .icon,
.sidebar.open .logo-details .logo_name {
  opacity: 1;
}

.sidebar i {
  color: #fff;
  height: 60px;
  min-width: 50px;
  font-size: 28px;
  text-align: center;
  line-height: 60px;
}

.sidebar .nav-list {
  margin-top: 20px;
  height: 100%;
}

.sidebar li {
  position: relative;
  margin: 8px 0;
  list-style: none;
}

.sidebar li .tooltip {
  position: absolute;
  top: -20px;
  left: calc(100% + 15px);
  z-index: 3;
  background: #fff;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.3);
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 15px;
  font-weight: 400;
  opacity: 0;
  white-space: nowrap;
  pointer-events: none;
  transition: 0s;
}

.sidebar li:hover .tooltip {
  opacity: 1;
  pointer-events: auto;
  transition: all 0.4s ease;
  top: 50%;
  transform: translateY(-50%);
}

.sidebar.open li .tooltip {
  display: none;
}

.sidebar li a {
  display: flex;
  height: 100%;
  width: 100%;
  border-radius: 12px;
  align-items: center;
  text-decoration: none;
  transition: all 0.4s ease;
  background: #3C58A6;
}

.sidebar li a:hover {
  background: #1A274A;
}

.sidebar li a .links_name {
  color: #fff;
  font-size: 15px;
  font-weight: 400;
  white-space: nowrap;
  opacity: 1;
  pointer-events: none;
  transition: 0.4s;
  margin-left: 15px;
  overflow: hidden;
}

.sidebar li a:hover .links_name,
.sidebar li a:hover i {
  transition: all 0.5s ease;
  color: #fff;
}

.sidebar li i {
  height: 50px;
  line-height: 50px;
  font-size: 18px;
  border-radius: 12px;
}

.sidebar li.profile {
  position: fixed;
  height: 60px;
  width: 78px;
  left: 0;
  bottom: -8px;
  padding: 10px 14px;
  transition: all 0.5s ease;
}

.sidebar.open li.profile {
  width: 205px;
}

/* ===== MEDIA QUERIES=====*/

@media (max-width: 1000px) {
  td:not(:first-of-type) {
    min-width: rem;
  }
}

@media screen and (min-width: 768px) {
  body {
    margin: calc(var(--header-height) + 1rem) 0 0 0;
    padding-left: calc(var(--nav-width) + 2rem);
  }


  .header {
    height: calc(var(--header-height) + 1rem);
    padding: 0 2rem 0 calc(var(--nav-width) + 2rem);
  }

  .header__img {
    width: 40px;
    height: 40px;
  }

  .header__img img {
    width: 45px;
  }

  /*Show navbar desktop*/
  .open {
    width: calc(var(--nav-width) + 136px);
  }

  /*Add padding body desktop*/
  .body-pd {
    padding-left: calc(var(--nav-width) + 160px);
  }
}

@media screen and (max-width: 760px) {

  .sidebar {
    transform: translate(-100%);
  }

  .sidebar.open {
    transform: translateX(0.1%);
  }

  .sidebar.open li.profile {
    width: 78px;
  }

  i.bx-x {
    margin-left: 80px;
    transition: all 0.5s ease;
  }

  i {
    transition: all 0.5s ease;
  }

}
</style>