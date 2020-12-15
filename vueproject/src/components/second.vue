<template>
    <div>
        <p>
            I am in {{anotherName}}
            <br/>
            I am {{age}} years old.
        </p>
        
    </div>
</template>
<script>
export default {
    name: "Second",
    props: ["anotherName", "age"],
}
</script>