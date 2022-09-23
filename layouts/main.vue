<template>
    <div>
        <b-navbar toggleable="lg" type="dark" variant="info">
            <b-navbar-brand>
                <nuxt-link to="/" exact>Home</nuxt-link>
            </b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>
                    <nuxt-link to="/run-button">Escape button</nuxt-link>
                </b-navbar-nav>
                <b-navbar-nav>
                    <nuxt-link to="/svg-icon">Svg icon</nuxt-link>
                </b-navbar-nav>
                <b-navbar-nav>
                    <nuxt-link to="/testing">testing</nuxt-link>
                </b-navbar-nav>
            </b-collapse>
        </b-navbar>
        <Nuxt />
    </div>
</template>

<style>
a {
    margin-left: 20px;
    color: white;
    text-decoration: none;
}

a:hover {
    color: white;
    text-decoration: none;
}
</style>