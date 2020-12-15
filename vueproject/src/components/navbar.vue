<template>
<div>
    <nav class="navbar navbar-inverse shadow-sm">
        <div class="container">
            <div class="navbar-header">
                <h1 class="navbar-brand m-3"><span class="text-danger">WebSi</span><span class="text-warning">teName</span></h1>
            </div>
            <div class=" navbar-expand" id="myNavbar">
                <ul class="nav navbar-nav">
                    <li><a href="#home" class="active">HOME</a></li>
                    <li><a href="#aboutus"><b>ABOUT US</b></a></li>
                    <li><a href="#cafe">CAFE</a></li>
                    <li><a href="#wedding">WEDDINGS</a></li>
                    <li><a href="#training">TRAINING</a></li>
                    <li class="dropdown"><a href="#" class="dropdown-toggle" data-toggle="dropdown">SHOP<span class="caret"></span></a>
                        <ul class="dropdown-menu">
                            <li><a href="#shop1">SHOP 1</a></li>
                            <li><a href="#shop2">SHOP 2</a></li>
                        </ul>
                    </li>
                    <li><a href="#gallery">GALLERY</a></li>
                    <li><a href="#contact">CONTACT</a></li>
                </ul>
            </div>
            <div class="bg-danger">
            <span class="">o</span>
            </div>    
        </div>
    </nav> 
</div>
       
</template>

<script>
export default {
    name: "Navbar",
    props: [],
    components: {
       
    }
}
</script>

<style>
.navbar-inverse {
    background-color:#ffffff;
    position: fixed;
    top: 0;
    width: 100%;
}

.navbar-expand ul li a {
    color: black;
    text-decoration: none;
    padding: 14px 18px;
    text-align: center;
    font-size: 14px;
}
.navbar-expand ul li a:hover:not(active) {
    background-color: #555;
    color: #ffffff;
}

li:last-child {
    border-right: 1px solid #555;
}

.active {
    background-color: grey;
    font-size: 14px;

}
</style>