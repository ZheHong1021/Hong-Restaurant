<template>
    <footer>
        <div class="footer-item">
            <h1 class="footer-title">Hong Food</h1>
            <div class="flex flex-row gap-4 mt-4">
                <p class="footer-content">
                    <a href="#"><i class="fab fa-facebook"></i></a>
                </p>
                <p class="footer-content">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                </p>
                <p class="footer-content">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </p>
            </div>
        </div >
        <div class="footer-item">
            <h1 class="footer-title">聯絡資訊</h1>
            <p class="footer-content">地址: 高雄市XX區XX路45號</p>
            <p class="footer-content">電話: 0978-392-397</p>
            <p class="footer-content">負責人: 林哲弘</p>
        </div>
        <div class="footer-item">
            <h1 class="footer-title">服務資訊</h1>
            <p class="footer-content">暫無開放</p>
        </div>
        <div class="footer-item">
            <h1 class="footer-title">促銷活動</h1>
            <p class="footer-content">暫無開放</p>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer',

}
</script>

<style>
    footer{
        box-shadow: var(--section-shadow);
        padding: 1rem;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
        padding: 4rem 2rem;
}
    .footer-item{
        line-height: 1.5rem;
    }

    .footer-item .footer-title{
        font-size: var(--general-size);
        font-weight: 600;
    }
    .footer-item .footer-content{
        font-size: var(--content-size);
    }

    @media screen and (min-width: 768px) {
        footer{
            grid-template-columns: repeat(4, 1fr);
            justify-items: center;
        }
   
    }

</style>