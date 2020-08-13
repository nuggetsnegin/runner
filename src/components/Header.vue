<template>
    <header class="flex items-center">
        <span class="logo"><img src="../assets/iconLogo.svg" alt="Company logo"></span>
        <nav>
            <ul class="flex text-lg antialiased text-gray-800">
                <li class="mr-12"><a href="#">Home</a></li>
                <li class="mr-12"><a href="#" class="line-through">Shop</a></li>
                <li class="mr-12"><a href="#">Blog</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>

        <div class="search-profile-cart">
            <ul class="flex space-between">
                <li class="mr-2"><a href="#"><img src="../assets/iconSearch.svg" alt="Search icon"></a></li>
                <li class="mr-2"><a href="#"><img src="../assets/iconAccount.svg" alt="Account icon"></a></li>
                <li class="mr-2"><a href="#"><img src="../assets/iconCart.svg" alt="Cart icon"></a></li>
            </ul>
        </div>
    </header>
</template>

<style scoped>
    header {
        border-width: 0 0 2px;
        --border-opacity: 1;
        border-color: #edf2f7;
        border-color: rgba(237,242,247,var(--border-opacity));
        margin-bottom: 2rem;
        height: 7vh;
        justify-content: space-between;
    }
    
</style>