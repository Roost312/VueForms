<template>
    <div>
        <div class="form-group">
            <label for="name">Name</label>
            <input class="form-control" :value="named" @input="$emit('input', $event.target.value)" type="text" placeholder="full name">
        </div>
    </div>
</template>

<script>
export default {
    props: ['named']
}
</script>

