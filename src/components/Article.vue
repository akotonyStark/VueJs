<template lang="">
    <div>
        <h2>Article Component</h2>
        <h4 v-bind="$attrs">Article: {{title}} </h4>
        <h4>Likes: {{numberOfLikes}}</h4>
        <h4>Published: {{isPublished ? 'Yes' : 'No'}}</h4>
    </div>
</template>
<script>
export default {
    name: 'ArticleComponent',
    props: {
        title: {
            type: String,
            required: true,
            default: 'Article Default Title'
        },
        numberOfLikes: Number,
        isPublished: Boolean
    },
    inheritAttrs: false
}
</script>
