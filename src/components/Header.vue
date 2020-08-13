<template>
    <header>
        <div class="logo items-center"><img src="../assets/iconLogo.svg" alt="Company logo"></div>
        <nav>
            <ul class="flex items-center justify-between">
                <li><a href="#">Home</a></li>
                <li><a href="#">Shop</a></li>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>

        <div class="search-profile-cart">
            <ul>
                <li><a href="#"><img src="../assets/iconSearch.svg" alt="Search icon"></a></li>
                <li><a href="#"><img src="../assets/iconAccount.svg" alt="Account icon"></a></li>
                <li><a href="#"><img src="../assets/iconCart.svg" alt="Cart icon"></a></li>
            </ul>
        </div>
        <hr>
    </header>
</template>

<style scoped>
    hr{
        border-width: 0 0 2px;
        border-color: #edf2f7;
        border-color: rgba(237,242,247,var(--border-opacity));
        margin-top: 2rem;
        margin-bottom: 4rem;
    }
</style>