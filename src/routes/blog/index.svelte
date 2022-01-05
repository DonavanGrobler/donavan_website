<h1>Donavan's Blog Page</h1>

<script context="module">
    const allPosts = import.meta.glob('./*.md');

    let blog = [];

    for (let path in allPosts) {
        blog.push (
            allPosts[path]().then(({metadata}) => { 
                return {path, metadata};
            })
        );
    }

    // console.log('blog=', blog);

    export const load = async() => {
        const posts = await Promise.all(blog);
        return {
            props: {
                posts,
            }
        }
    };
</script>

<script>
    export let posts;
    import Article from "$lib/Article.svelte";
    // console.log('posts=', posts);
</script>

<div>
    {#each posts as post}
        <Article {post}/>
    {/each}
</div>




