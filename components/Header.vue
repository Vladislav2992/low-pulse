<script setup>
const isMenuOpen = ref(false)
</script>
<template>
    <header class="header">
        <div class="container">
            <RouterLink to="/" class="logo">
                <img src="/logo.svg" alt="">
            </RouterLink>

            <nav :class="{'header__menu':true, 'active' : isMenuOpen}">
                <ul class="menu">
                    <li class="menu__item with-children">
                        <RouterLink to="/">Мониторинг</RouterLink>
                        
                        <div class="children__menu-wrapper">
                            <ul class="children__menu">
                                <li class="children__item">
                                    <RouterLink to="/">Мониторинг сервера</RouterLink>
                                </li>
                                <li class="children__item">
                                    <RouterLink to="/">DNS мониторинг</RouterLink>
                                </li>
                                <li class="children__item">
                                    <RouterLink to="/">Мониторинг сайта</RouterLink>
                                </li>
                                <li class="children__item">
                                    <RouterLink to="/">Сердцебиение</RouterLink>
                                </li>
                                <li class="children__item">
                                    <RouterLink to="/">Кастомные домены</RouterLink>
                                </li>
                            </ul>
                        </div>
                    </li>
                    <li class="menu__item">
                        <RouterLink to="/">Проекты</RouterLink>
                    </li>
                    <li class="menu__item">
                        <RouterLink to="/">Статус</RouterLink>
                    </li>
                    <li class="menu__item">
                        <RouterLink to="/">Цены</RouterLink>
                    </li>
                </ul>

                
                <div class="header__buttons">
                    <button class="btn btn_border-white">Зарегестрироваться</button>
                    <button class="btn btn_white">Войти</button>
                </div>
            </nav>

            <div :class="{'burger':true, 'active' : isMenuOpen}" @click="isMenuOpen = !isMenuOpen">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </header>

</template>

<style lang="scss" scoped>
.header {
    padding: 14px 0;
    background: var(--blue);
    color: var(--white);
    border: 1px solid rgba(102, 110, 170, 0.3);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 5;
}
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
}

.header__menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 80%;
}
.burger {
    display: flex;
    flex-direction: column;
    gap: 5px;
    width: 23px;
    display: none;

    span {
        display: block;
        width: 100%;
        height: 3px;
        background: var(--white);
        border-radius: 2px;
        transition: transform .3s;
    }
}

.menu {
    display: flex;
    gap: 34px;
}
.menu__item a {
    font-weight: 700;
    padding: 6px 18px;
    border-radius: 39px;
    background-color: inherit;
    transition: background .3s;

    &:hover {
        background-color: #363B59;
    }
}

.with-children  {
    position: relative;

    &:hover .children__menu-wrapper {
        transform: translateY(0);
        opacity: 1;
        visibility: visible;
    }
}
.with-children a {
    position: relative;
    padding-right: 40px;

    &::after {
        content: '';
        position: absolute;
        width: 12px;
        height: 7px;
        right: 18px;
        top: 13px;
        background: url('../assets/img/arrow-down.svg') no-repeat;
        transform: rotate(180deg);
        transition: transform .3s;
        transform-origin: 50%;
    }

    &:hover:after {
        transform: rotate(0);
    }
}
.children__menu-wrapper {
    position: absolute;
    padding-top: 10px;
    top: 100%;
    transform: translateY(-10%);
    opacity: 0;
    visibility: hidden;
    transition: transition .3s, opacity .3s;        
}
.children__menu {
    background-color: var(--white);
    padding: 14px 10px;
    border-radius: 8px;
    width: 293px;
    display: flex;
    gap: 8px;
    flex-direction: column;
}
.children__item a {
    display: block;
    color: var(--blue);
    font-size: 15px;
    font-weight: 400;
    padding: 6px 15px 7px 29px;
    border-radius: 30px;

    &::before {
        content: '';
        position: absolute;
        left: 15px;
        top: 14px;
        width: 4px;
        height: 4px;
        border-radius: 50%;
        background: var(--light-blue);
    }

    &::after {
        content: none;
    }
    
    &:hover {
        background: rgba(20, 86, 255, .1); 
    }
}
.header__buttons {
    display: flex;
    gap: 20px;

    .btn {            
        padding: 10px 25px;
    }
}


@media (max-width: 1084px) {
    .header__menu {
        position: absolute;
        top: 47px;
        left: -2px;
        right: -2px;
        bottom: 0;
        height: calc(100dvh - 61px);
        width: 100%;
        z-index: 5;
        background: var(--blue);
        display: flex;
        flex-direction: column;
        align-items: baseline;
        padding: 25px 15px 40px 15px;
        transition: .3s;
        transform: translateX(120%);
        opacity: 0;
        visibility: hidden;

        &.active {
            transform: translateX(0);
            opacity: 1;
            visibility: visible;
        }

    }
    .burger {
        display: flex;

        &.active {
            span:nth-child(1) {
                transform: translate(-4px, 6px) rotate(45deg);
                width: 26px;
            }
            span:nth-child(2) {
                opacity: 0;
            }
            span:nth-child(3) {
                transform: translate(-3px, -10px) rotate(-45deg);
                width: 26px;
            }
        }        
    }
    .menu {
        flex-direction: column;
        width: 100%;
    }
    .menu__item a {
        padding: 0;
        font-weight: 600;
        margin-bottom: 30px;

        &:hover {
            background-color: transparent;
        }
    }
    .children__menu-wrapper {
        position: static;
        color: inherit;
        opacity: 1;
        visibility: visible;
        transform: translate(0);
        padding: 0;
    }
    .children__menu {
        padding: 0;
        width: 100%;
        background: transparent;
        border-radius: 0;
        border-bottom: 1px solid rgba(151, 152, 154, .3);
    }
    .children__item a {
        color: var(--white);
        padding: 0;
        margin-bottom: 25px;

        &::before {
            content: none;
        }
    }
    .with-children > a {
        font-size: 20px;
        font-weight: 700;
        display: block;
        margin-bottom: 25px;
        &::after {
            content: none;
        }
    }
}
@media(max-width: 500px) {
    .header__buttons {
        width: 100%;
        gap: 10px;
    }
    .header__buttons {
        flex-direction: column;
    }
}
</style>