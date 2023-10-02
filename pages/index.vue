<template>
    <ContainerProfile 
        :name=profileInformation().name
        :job=profileInformation().job 
        :srcPhoto=profileInformation().srcPhoto
        :mail=profileInformation().mail
        :location=profileInformation().location 
        :contacts=profileInformation().contacts />
</template> 

<script setup lang="js">


const portfolio_information = "portfolioInformation.json"
// data: () => ({
//     posts: []
// })

// const { data, pending, error, refresh } = await useAsyncData(
//   'mountains',
//   () => $fetch(portfolio_information)
// )

// console.log(data)



// const { data, pending, error, refresh} = await useFetch(portfolio_information)
// console.log(pending)
// console.log(data)


// const users = await $fetch(portfolio_information).catch((error) => error.data)


// async function pp() {
//     const response = fetch(portfolio_information)
//     const iff = (await response).json()
//     return iff
// }

// const n = computed(() => {
//     return pp().then(mm => mm)
// })
// pp().then(mm => mm)
// console.log(n.value)


// fetch(portfolio_information)
//     .then(response => response.json())
//     .then(function(data){
//         let info = data
//         console.log(info)
//     })
//     .catch(err => console.log('Solicitud fallida', err))

</script>

<!-- <NuxtLayout>
        <div>
            <h1>Welcome to the homepage</h1>
            <AppAlert>
                This is an auto-imported component
            </AppAlert>
            <ImagenesFotoPerfil src="/img/foto_perfil.jpg" />
        </div>
        <Icon name="ic:baseline-person-pin" class="icon_1"/>
    </NuxtLayout> -->

<!-- <script setup lang="ts">

// This will work in both `<script setup>` and `<script>`
definePageMeta({
    layout: 'default'
});
</script>

<style>
.icon_1{
    border: 1px solid red;
    width: 100px;
    height: 100px;
    color: blue;
    background-color: brown;
}
</style> -->