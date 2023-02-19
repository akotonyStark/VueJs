<template lang="en">
    <div>
        <h2>Hello {{name}} also known as {{heroName}}</h2>
    </div>
</template>


<script>
export default {
    name:'HeroNames',
    props: ['name', 'heroName']
}
</script>
