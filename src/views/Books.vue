<template>
    <div>
        <v-list dense>
                <v-list-item
            v-for="(item, i) in books"
            :key="i"
        >
            <v-list-item-avatar>
            <v-img
                :src="item.img"
            ></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
                <v-list-item-subtitle>{{ item.author.name }}</v-list-item-subtitle>
                <v-list-item-subtitle>{{ item.price }}</v-list-item-subtitle>
                <v-list-item-subtitle>Pages: {{ item.pages }}</v-list-item-subtitle>    
            </v-list-item-content>

            <v-list-item-icon>
            <v-icon>
                status
            </v-icon>
            </v-list-item-icon>
        </v-list-item>
    </v-list>
    </div>
</template>

<script>
    import booksList from '@/data/books.json'
    export default {
        data()
        {
            return {
                books:booksList
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>