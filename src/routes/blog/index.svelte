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

    console.log('blog=', blog);

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
    console.log('posts=', posts);
</script>

<div>
    {#each posts as {path, metadata}}
        <article>
            <h2>
                {metadata.title}
            </h2>
            <p>
                {metadata.description}
            </p>
            <a href={`/blog/${path.replace(".md", "")}`}>
                Read More
            </a>
            <img src="{metadata.image}" alt="Remember to add descripion">
        </article>
    {/each}
</div>

<h1>Donavan's Blog Page</h1>


