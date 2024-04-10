<template>
    <section class="join">
        <div class="container">
            <div class="img-wrapper">
                <img src="/benefits/4.png" alt="">
            </div>
            <div class="text">
                <h2 class="section__title">Присоединяйтесь <br> к нам в мобильном приложении</h2>
                <p>Получайте уведомления, управляйте мониторами и проверяйте статистику вашего сервера в любом месте.</p>
                <div class="download-links">
                    <a href="#!"><img src="/appstore.svg" alt=""></a>
                    <a href="#!"><img src="/googleplay.svg" alt=""></a>
                </div>
            </div>
        </div>
    </section>
</template>
<style lang="scss" scoped>
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    align-items: center;
}
.img-wrapper {
    transform: translateX(-72px);
}

.section__title {
    text-align: left;
    margin-bottom: 30px;
}
.text p {
    font-size: clamp(16px, 4vw, 20px);
    color: rgba(0,0,0, .4);
    font-weight: 600;
    line-height: 150%;
    margin-bottom: 37px;
}
.download-links {
    display: flex;
    gap: 13px;
}

@media(max-width: 1200px) {
    .img-wrapper {
        transform: translateX(0);
    }
}
@media(max-width: 890px) {
    .container {
        display: flex;
        flex-direction: column;
        gap: 42px;
    }
    .section__title {
        text-align: center;
        margin-bottom: 5px;
    }
    .text {
        display: flex;
        flex-direction: column;
        order: 1;
        align-items: center;
        text-align: center;

        p {
            margin-bottom: 24px;
        }
    }
    .img-wrapper {
       order: 2;
    }

}
</style>