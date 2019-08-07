<template>
    <!-- <a @click="alert">click me</a> -->
    <form id="content" class="absolute bottom-0 right-0 z-50 -mr-32">
        <input type="text" name="input" class="input" id="search-input"  :class="toggleInput">
        <button type="reset" class="search" id="search-btn"  @click="toggleState" :class="toggleButton"></button>
    </form>
</template>

<script>

export default {
    name: "Search",
    data(){
        return {
            isOpen: true
        };
    },
    methods: {
        toggleState: function(){
            this.isOpen = !this.isOpen;
        }
    },
    computed: {
        toggleInput: function(){
            return {
                'square': !this.isOpen
            };
        },
        toggleButton: function(){
              return {
                'close': !this.isOpen
            };
        }
    }
}

</script>