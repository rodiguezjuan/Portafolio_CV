<template>
    <div class="container">
        <div class="container-top">
            <h2>
                {{ props.name }}
            </h2>

            <p>
                {{ props.job }}
            </p>
        </div>
        <figure>
            <img :src=props.srcPhoto :alt=text_alt height="250">
        </figure>

        <p>
            {{ props.mail }}
        </p>

        <p>
            {{ props.location }}
        </p>

        <ul>
            <li v-for="contact in props.contacts">
                <Icon :name=contact.icon class="icon_1" />
            </li>
        </ul>

        <button>Hire me</button>
    </div>
</template>

<script setup lang="js">
const props = defineProps(
    {
        name: String,
        job: String,
        srcPhoto: String,
        mail: String,
        location: String,
        contacts: Array,

    }
)

const text_alt = ref("profile photo of " + props.name)

</script>

<style>
.container {
    --dimension_x: 350px;
    --dimension_y: ;

    width: var(--dimension_x);
    padding: 24px;
    margin: 0;


    border: 1px solid red;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.container-top{
    width: 100%;
    /* padding: 24px; */

    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;

    border: 1px solid green;
}
.container-top h2{
    width: 60%;
    /* margin: 0;
    margin-right: 12px;
    padding: 0; */

    border: 1px solid blue;

    font-size: 24pt;
    
}

.container-top p{
    width: 30%;
    /* margin: 0;
    margin-left: 12px;
    padding: 0; */

    border: 1px solid blueviolet;
    
    font-size: 12pt;

}
</style>