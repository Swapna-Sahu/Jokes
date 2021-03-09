<template>
    <div>
        <h1>About Jokes</h1>
        <p>A joke is a short humorous piece of oral literature in which the funniness culminates in the final sentence, called the punchline… In fact, the main condition is that the tension should reach its highest level at the very end. No continuation relieving the tension should be added. As for its being "oral," it is true that jokes may appear printed, but when further transferred, there is no obligation to reproduce the text verbatim, as in the case of poetry</p>
    </div>
    
</template>
<script>
export default {
    head() {
        return {
            title:'About The App',
            meta: [
                {
                    hid: 'decription',
                    name: 'description',
                    content: 'Best places for the jokes'
                }
            ]
        }
    },
}
</script>
<style>
p{
    margin-block: 20px;
    background-color: whitesmoke;
    text-align: justify;
    padding: 15px;
}
</style>
