<template>
    <div class="background-nav">
        <b-container class="h-100">
            <b-navbar class="h-100 py-0 navbar_position d-flex p-0">
                <ul id="nav_navbar" class="d-flex justify-content-between align-items-center h-100 w-100">
                    <li class="align-items-center h-100 d-flex navbar-link text-white showHover" href="#">
                        <a class="text-white p-4 " href="#">{{list_navbar.link_catolog}}</a>
                        <!-- Сделать анимацию выпадающего меню -->
                        <ul class="dropdown-list bg-white">
                            <li class="dropdown-list__item d-flex align-items-center">
                                <a @mouseover="showRoate90degrees()" @mouseout="showDefaultRoate()"
                                    class="text-decoration-none w-100 py-3 px-4 text-dark  d-flex justify-content-between"
                                    href="#">{{list_catalog.item1}} <span class="navbar-dropdown__triangle"
                                        :class="{roate90degrees: classObjectTriangle.positionTriangle}">►</span></a>
                            </li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center text-dark"> <a
                                    @mouseover="showRoate90degrees()" @mouseout="showDefaultRoate()"
                                    class="text-decoration-none w-100 py-3 px-4 text-dark  d-flex justify-content-between"
                                    href="#">{{list_catalog.item2}} <span class="navbar-dropdown__triangle"
                                        :class="{roate90degrees: classObjectTriangle.positionTriangle}">►</span></a>
                            </li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    @mouseover="showRoate90degrees()" @mouseout="showDefaultRoate()"
                                    class="text-decoration-none w-100 py-3 px-4 text-dark  d-flex justify-content-between"
                                    href="#">{{list_catalog.item3}} <span class="navbar-dropdown__triangle"
                                        :class="{roate90degrees: classObjectTriangle.positionTriangle}">►</span></a>
                            </li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    class="text-decoration-none w-100 py-3 pl-4 text-dark "
                                    href="#">{{list_catalog.item4}}</a></li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    class="text-decoration-none w-100 py-3 pl-4 text-dark "
                                    href="#">{{list_catalog.item5}}</a></li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    class="text-decoration-none w-100 py-3 pl-4 text-dark "
                                    href="#">{{list_catalog.item6}}</a></li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    class="text-decoration-none w-100 py-3 pl-4 text-dark "
                                    href="#">{{list_catalog.item7}}</a></li>
                            <hr class="hr">
                            <li class="dropdown-list__item d-flex align-items-center"><a
                                    class="text-decoration-none w-100 py-3 pl-4 text-dark "
                                    href="#">{{list_catalog.item8}}</a></li>
                            <hr class="hr">
                        </ul>
                    </li>
                    <li class="d-flex navbar-link text-white" href="#">
                        <a class="p-4 text-white " href="#">{{list_navbar.link_kolerovka}}</a>
                    </li>
                    <li class="d-flex navbar-link text-white" href="#">
                        <a class="p-4 text-white " href="#">{{list_navbar.link_decor}}</a>
                    </li>
                    <li class="d-flex navbar-link text-white" href="#">
                        <a class="p-4 text-white " href="#">{{list_navbar.link_blog}}</a>
                    </li>
                    <li class="d-flex navbar-link text-white" href="#">
                        <a class="p-4 text-white " href="#">{{list_navbar.link_contacts}}</a>
                    </li>

                    <div class="icon-block"></div>
                </ul>
                <ul class="p-0 m-0 d-flex">
                    <li><a class="navbar__linkSVG p-4" href="#">
                            <app-svgUser></app-svgUser>
                        </a>
                    </li>
                    <li>
                        <a class="navbar__linkSVG p-4" href="#">
                            <app-svgLike></app-svgLike>
                        </a>
                    </li>
                    <li>
                        <a class="navbar__linkSVG p-4" href="#">
                            <app-svgTrash></app-svgTrash>
                        </a>
                    </li>
                </ul>
            </b-navbar>
        </b-container>
    </div>
</template>
<script>
    import svgUser from './UserSVG.vue';
    import svgLike from './LikeSVG.vue';
    import svgTrash from './TrashSVG.vue';
    export default {
        components: {
            'app-svgUser': svgUser,
            'app-svgLike': svgLike,
            'app-svgTrash': svgTrash,
        },
        data() {
            return {
                list_catalog: {
                    item1: 'Краска',
                    item2: 'Эмали',
                    item3: 'Декоративные краски',
                    item4: 'Штукатурки',
                    item5: 'Лаки и масла',
                    item6: 'Покрытие для дерева',
                    item7: 'Инструменты',
                    item8: 'Акции',
                },
                list_navbar: {
                    link_catolog: 'Каталог',
                    link_kolerovka: 'Коллеровка',
                    link_decor: 'Декорирование интерьеров',
                    link_blog: 'Блог',
                    link_contacts: 'Контакты',
                },
                classObjectTriangle: {
                    positionTriangle: false,
                },
            }
        },
        methods: {
            showRoate90degrees() {
                this.classObjectTriangle.positionTriangle = true
            },
            showDefaultRoate() {
                this.classObjectTriangle.positionTriangle = false
            }
        },
        created() {
            const collectionListsLink = document.querySelectorAll('.dropdown-list ');
            console.log(collectionListsLink)
        },
    }
</script>

<style lang="scss" scoped>
    $background_color_nav: #336a73;
    $color-white: #fff;
    $link-color: #f5be19 !important;

    ul {
        list-style: none;
    }

    .navbar-link a {
        cursor: pointer;
        color: $color-white;
    }

    .dropdown-list__item {
        width: 300px;
    }

    .hr {
        margin: 0px;
    }

    .navbar_position {
        position: relative;
    }

    .dropdown-list {
        display: none;
        padding: 0;
        transition: 0.3s;
        position: absolute;
        top: 115px;
        z-index: 1;
    }

    .dropdown-list__item {
        z-index: 1;
    }

    #nav_navbar {
        padding: 0;
        margin: 0px;
    }

    .showHover,
    .showHover a {
        position: relative;
        z-index: 1;
    }

    .showHover a:hover {
        color: $link-color;
    }

    #nav_navbar .showHover:hover ul {
        display: block;
        transition: 0.3s;
        z-index: 1;
    }

    .background-nav {
        background-color: $background_color_nav;
        width: 100%;
        height: 115px;
    }

    .navbar-dropdown__triangle {
        transition: 0.3s;
    }

    .roate90degrees {
        transform: rotate(90deg);
        transition: 0.3s;
    }
</style>