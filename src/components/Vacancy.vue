<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="box mt-4 mb-4">
        <h1 class="title is-5">{{vacancy.title}}</h1>
        <span>{{vacancy.company}}</span>
        <p>{{vacancy.city}}</p>
        <br/>
       <p>{{vacancy.description}}</p>
       <div class="is-flex is-justify-content-space-between">
         <button @click="handleApply(vacancy)" class="button is-primary mt-4 mr-4" >Apply</button>
         <button v-if="isAdmin" @click="handleDelete(vacancy)" class="button is-danger">Remove</button>
       </div>
    </div>
</template>

<script>
export default {
// eslint-disable-next-line vue/multi-word-component-names
name: 'Vacancy',
props: {
    vacancy:{
        type: Object,
        required: true
    },
    isAdmin:{
        type: Boolean,
        required:true
    }
},
methods: {
    handleDelete(vacancy){
        this.$emit('delete',vacancy.id)
    },
    handleApply(vacancy){
        window.alert(`Applied Successfully for ${vacancy.title}`)
    }
}

}
</script>

<style lang="scss" scoped>
</style>