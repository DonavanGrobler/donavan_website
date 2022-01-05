<script>
    export let post;
    console.log(post);
</script>

<article>
    <img src="{post.metadata.image}" alt="Blog Post">
    <h2>
        {post.metadata.title}
    </h2>
    <p>
        {post.metadata.description}
    </p>
    <a href={`/blog/${post.path.replace(".md", "")}`}>
        Read More
    </a>
</article>

<style>
    article {
        display: flex;
        grid-template-columns: 1fr 2fr;
        padding: 1rem;
 
    }
    img {
        border-radius: 2rem;
        width: 150px;
        height: 100px;
    }
    a {
        margin: 0;
        display: flex;
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>