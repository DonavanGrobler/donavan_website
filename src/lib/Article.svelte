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
            <a href={`/blog/${post.path.replace(".md", "")}`}>
                Read More
            </a>
    </p>
    
</article>

<style>
    article {
        display: inline-block;
        grid-template-columns: 1fr 2fr;
        padding: 1rem;
        margin: 5px;
 
    }
    img {
        border-radius: 2rem;
        width: 200px;
        height: 150px;
    }
    a {
        display: flex;
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 0.85rem;
    }
    h2 {
        font-size: 2rem;
    }
    p {
        font-size: 1.5rem;
    }

</style>