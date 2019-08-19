<template>
    <form v-on:submit.prevent="bookSubmit(bookTitle,bookAuthor)"  class="" action="#" method="post">
        <input v-model="bookTitle" type="text" value="" placeholder="Book Title">
        <input v-model="bookAuthor" type="text" value="" placeholder="Book Author">
        <button type="submit" name="button">Add Book</button>
    </form>
</template>
<script>

import BookItem from './BookItem';
export default {
    name: 'BookForm',
    props: ['books'],
    components:{
        BookItem
    },
    data() {
        return {
            bookTitle:  '',
            bookAuthor: ''
        }
        
    },
    methods:{
        bookSubmit(bookTitle,bookAuthor) {
            this.$emit('addBook', bookTitle,bookAuthor);
        }
    }
    
}
</script>
<style>
</style>