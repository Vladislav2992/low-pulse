<template>
    <aside class="aside">
        <div class="container">
            <div class="left">
                <h2 class="title">Мы сделали 20 проверок для 5 мониторов. Также у нас есть 65 страниц статуса.</h2>
                <div class="input-wrapper">
                    <input type="text" class="input" placeholder="Ваш сайт">
                    <button class="hook">Подключить мониторинг</button>
                </div>            
            </div>
            <div class="img">
                <img src="/aside-1.png" alt="">
            </div>
        </div>
    </aside>
</template>
<style lang="scss" scoped>

.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    background: var(--blue) url('../assets/img/main-bg.png') no-repeat;
    background-size: cover;
    border-radius: 10px;
    padding: 30px 50px;
    overflow: hidden; 
    position: relative;
    max-width: 1240px;
  
    &::after {
        content: '';
        position: absolute;
        bottom: 5px;
        left: 0;
        right: 0;
        background: url('../assets/img/puls-line.svg') no-repeat;
        background-position: 0 -3px;
        background-size: cover;
        height: 44px;
    }
}
.title {
    color: var(--white);
    font-weight: 600;
    font-size: clamp(24px, 5vw, 32px);
    line-height: 130%;
    font-family: 'Jost', sans-serif;
    margin-bottom: 20px;
}
.input-wrapper {    
    border-radius: 42px;
    width: 100%;
    height: 52px;
   
    background: #232642, var(--white);
    position: relative;
}
.input {
    border: none;
    border-radius: 42px;
    padding: 14px 30px;
    width: 100%;
    height: 100%;
    border: 1px solid rgba(102, 110, 170, 0.3);
    box-shadow: 0 5px 17px 0 rgba(255, 255, 255, 0.2);
}

.hook {
    position: absolute;
    padding: 12px 36px;
    font-size: 15px;
    font-weight: 600;
    color: var(--blue);
    width: fit-content;
    border: 1px solid rgba(102, 110, 170, 0.3);
    border-radius: 42px;
    right: 5px;
    bottom: 4px;  transition: color .3s;

    &:hover {
        color: var(--light-blue);
    }
}

@media(max-width: 1100px) {
    .container {
        grid-template-columns: 1fr;
        padding: 20px;
    }
}
@media(max-width: 700px) {
    .container {
        margin-left: 20px;
        margin-right: 20px;
    }
    .input-wrapper {
        display: flex;
        flex-direction: column;
        gap: 10px;
        height: auto;
        margin-bottom: 20px;
    }
    .hook {
        position: static;
        width: 100%;
    }
}
</style>