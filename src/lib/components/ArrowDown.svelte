<div class="arrow-7">
    <span></span>
    <span></span>
    <span></span>
</div>

<style>
    .arrow-7 {
        margin: 0 auto;
        width: 38px;
        height: 100px;
    }
    .arrow-7 span {
        display: block;
        width: 30px;
        height: 30px;
        border-bottom: 2px solid #EA0029;
        border-right: 2px solid #EA0029;
        transform: rotate(45deg);
        margin: -16px 0;
        animation: arrow-7 2s infinite;
    }
    .arrow-7 span:nth-child(2) {
        animation-delay: -0.2s;
    }
    .arrow-7 span:nth-child(3) {
        animation-delay: -0.4s;
    }
    @keyframes arrow-7 {
        0% {
            opacity: 0;
            transform: rotate(45deg) translate(-20px, -20px);
        }
        50% {
            opacity: 1;
        }
        100% {
            opacity: 0;
            transform: rotate(45deg) translate(20px, 20px);
        }
    }
</style>