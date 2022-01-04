<script>
    export let post;
    console.log(post);
</script>

<article>
    <h2>
        {post.metadata.title}
    </h2>
    <p>
        {post.metadata.description}
    </p>
    <a href={`/blog/${post.path.replace(".md", "")}`}>
        Read More
    </a>
    <img src="{post.metadata.image}" alt="Remember to add descripion">
</article>

<style>
    article {
        display: flex;
    }
</style>