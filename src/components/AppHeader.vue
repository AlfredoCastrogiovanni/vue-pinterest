<script>
    export default {
        name: "AppHeader"
    }
</script>

<template>
    <header>
        <div class="container">
            <div class="wrapper">
                <div class="button-wrapper">
                    <div class="logo">
                        <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" aria-label="" class="g_1 gUZ U9O kVc" height="24" role="img" viewBox="0 0 24 24" width="24">
                            <path d="M0 12a12 12 0 0 0 7.73 11.22 12 12 0 0 1 .03-3.57l1.4-5.94S8.8 13 8.8 11.94c0-1.66.96-2.9 2.16-2.9 1.02 0 1.51.77 1.51 1.68 0 1.03-.65 2.56-.99 3.98-.28 1.19.6 2.16 1.77 2.16 2.12 0 3.76-2.24 3.76-5.47 0-2.86-2.06-4.86-5-4.86a5.17 5.17 0 0 0-5.39 5.18c0 1.03.4 2.13.9 2.73q.12.17.08.34l-.34 1.36q-.06.31-.4.16c-1.49-.7-2.42-2.88-2.42-4.63 0-3.77 2.74-7.23 7.9-7.23 4.14 0 7.36 2.95 7.36 6.9 0 4.12-2.6 7.43-6.2 7.43-1.21 0-2.35-.63-2.74-1.37l-.74 2.84a14 14 0 0 1-1.55 3.23A12 12 0 1 0 0 12"/>
                        </svg>
                    </div>
                    <button class="active">Homepage</button>
                    <button>Esplora</button>
                    <button>Crea</button>
                </div>
                <div class="input-control">
                    <div>
                        <svg xmlns="http://www.w3.org/2000/svg" aria-label="Icona di ricerca" class="BNH gUZ U9O kVc" height="16" role="img" viewBox="0 0 24 24" width="16"><path d="M10 16a6 6 0 1 1 .01-12.01A6 6 0 0 1 10 16m13.12 2.88-4.26-4.26a10 10 0 1 0-4.24 4.24l4.26 4.26a3 3 0 1 0 4.24-4.24"/></svg>
                    </div>
                    <input type="text" placeholder="Cerca">
                </div>
                <div class="user-wrapper">
                    <button>
                        <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" aria-label="" class="BNH gUZ U9O kVc" height="24" role="img" viewBox="0 0 24 24" width="24">
                            <path d="M19 7v6.17A10 10 0 0 1 22 19H2a10 10 0 0 1 3-5.83V7a7 7 0 1 1 14 0m-4 14a3 3 0 1 1-6 0z"/>
                        </svg>
                    </button>
                    <button>
                        <svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" aria-label="" class="Hn_ BNH gUZ U9O kVc" height="24" role="img" viewBox="0 0 24 24" width="24">
                            <path d="M18 12.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3m-6 0a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3m-6-3a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3M12 0a11 11 0 0 0-8.52 17.95l-1.46 5.43a.5.5 0 0 0 .73.55l5.08-2.75A10.98 10.98 0 0 0 23 11 11 11 0 0 0 12 0"/>
                        </svg>
                    </button>
                    <div class="user">
                        <div>
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M5 21C5 17.134 8.13401 14 12 14C15.866 14 19 17.134 19 21M16 7C16 9.20914 14.2091 11 12 11C9.79086 11 8 9.20914 8 7C8 4.79086 9.79086 3 12 3C14.2091 3 16 4.79086 16 7Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </div>
                        <div>
                            <svg aria-hidden="true" aria-label="" class="BNH gUZ U9O kVc" height="12" role="img" viewBox="0 0 24 24" width="12">
                                <path d="M20.16 6.65 12 14.71 3.84 6.65a2.27 2.27 0 0 0-3.18 0 2.2 2.2 0 0 0 0 3.15L12 21 23.34 9.8a2.2 2.2 0 0 0 0-3.15 2.26 2.26 0 0 0-3.18 0"></path>
                            </svg>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '@/assets/scss/partials/_variables.scss' as *;
@use '@/assets/scss/partials/_mixins.scss' as *;

header {
    padding: 0.3rem 1rem;

    .container {
        width: 100%;
        height: 80px;

        .wrapper {
            width: 100%;
            height: 100%;
            @include flex(start, center);

            
            .button-wrapper {
                @include flex();

                .logo {
                    width: 45px;
                    height: 45px;
                    padding: .6rem;

                    @include flex(center, center);

                    border-radius: 50%;
                    cursor: pointer;

                    svg {
                        fill: $primary-color;
                    }

                    &:hover {
                        background-color: #f0f0f0;
                    }
                }

                button {
                    padding: 14px 16px;
                    color: $text-color;
                    font-size: 15px;
                    font-weight: 600;
                    background-color: transparent;
                    border: none;
                    border-radius: 24px;
                    cursor: pointer;

                    &.active {
                        background-color: black;
                        color: white;
                    }
                }
            }

            .input-control {
                @include flex();
                width: 100%;

                div {
                    border-radius: 25px 0 0 25px;
                    padding: 15px 0 12px 12px;
                    border: none;
                    background-color: #f1f1f1;

                    svg {
                        fill: $icon-color;
                    }
                }

                input {
                    width: 100%;
                    border: none;
                    background-color: #f1f1f1;
                    border-radius: 0 25px 25px 0;
                    padding: .5rem .6rem;

                    &:focus-within {
                        outline: none;
                    }
                }
            }

            .user-wrapper {
                margin: 0 .5rem 0 1rem;
                @include flex(center, center);

                button {
                    width: 45px;
                    height: 45px;
                    border: none;
                    background: transparent;
                    padding: .6rem;
                    border-radius: 50%;
                    cursor: pointer;
                    
                    svg {
                        fill: $icon-color;
                    }
                    
                    &:hover {
                        background-color: #f0f0f0;
                    }
                }

                .user {
                    @include flex(space-between, center);

                    div:first-child {
                        width: 45px;
                        height: 45px;
                        padding: .6rem;
                        border-radius: 50%;
                        margin-right: .5rem;

                        &:hover {
                        background-color: #f0f0f0;
                        }
                    }
                }
            }
        }
    }
}
</style>