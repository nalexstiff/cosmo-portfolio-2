<template>
    <div class="navbar">
        <div class="navbar-contents">
            <div class="logo-container">
                <img class="logo-img" src="/cosmonas-sign.png" />
            </div>
            <div class="navlinks-container">
                <a class="navlink">backgrounds</a>
                <a class="navlink">video</a>
                <a class="navlink">contact</a>
                <a class="navlink">blog</a>
            </div>
        </div>
    </div>
    <div class="shadow"></div>
</template>

<style scoped>
.navbar {
    width: 100%;
    height: 230px;
    position: sticky;
    display: block;
    background-color: #e0e0e0;
}

.navbar-contents {
    margin: 0 120px 0 120px;
    height: 100%;
    display: flex;
    justify-content: space-between;
}

.navlinks-container {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.navlink {
    display: inline-block;
    margin-left: 60px;
    font-size: 36pt;
}

.logo-container {
    height: 100%;
}

.logo-img {
    margin-top: -16px;
}

.shadow {
    content: "";
    display: block;
    width: 100%;
    height: 100px;
    background-image: linear-gradient(black, rgba(0,0,0,0));
    opacity: 0.2;
}
</style>
