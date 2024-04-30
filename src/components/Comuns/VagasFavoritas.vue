<template>
    <div>
        <div><button class="btn btn-primary offcanvas-style" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight"
            aria-controls="offcanvasRight">Vagas favoritadas</button>
        </div>
        

        <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
            <div class="offcanvas-header">
                <h5 id="offcanvasRightLabel">Vagas favoritas</h5>
                <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas"
                    aria-label="Close"></button>
            </div>
            <div class="offcanvas-body">
                ...
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'VagasFavoritas'
}
</script>

<style scoped>
    .offcanvas-style{
        position: absolute;
        z-index: 1;
        top: 70px;
        right: 0px;
    }

</style>