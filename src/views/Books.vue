<template>
    
    <div>
        <app-header title="Books" tooltip="Add Books" @add="$router.push('/books/0')" @search="SearchInBooks($event)"></app-header>
        <v-list dense>
            <v-list-item v-for="(item, i) in books" :key="i">
                <v-list-item-avatar>
                    <v-img :src="item.img"></v-img>
                </v-list-item-avatar>

                <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                    <v-list-item-subtitle>{{ item.author.name }}</v-list-item-subtitle>
                    <v-list-item-subtitle>{{ item.price }}</v-list-item-subtitle>
                    <v-list-item-subtitle>Pages: {{ item.pages }}</v-list-item-subtitle>    
                </v-list-item-content>

                
                <v-list-item-icon>
                    <v-menu offset-y>
                    <template v-slot:activator="{ on, attrs }">
                        <v-btn
                        color="primary"
                        dark
                        v-bind="attrs"
                        v-on="on" text
                        >
                        <v-icon>mdi-dots-vertical</v-icon>
                        </v-btn>
                    </template>
                    <v-list>    
                        
                        <v-list-item>
                            <v-list-item-title @click="$router.push('/books/' + item._id)">Edit</v-list-item-title>
                        </v-list-item>
                    
                        <v-list-item>
                            <v-list-item-title>Delete</v-list-item-title>
                        </v-list-item>
                        <v-list-item>
                            <v-list-item-title>Issue</v-list-item-title>
                        </v-list-item>
                        <v-list-item>
                            <v-list-item-title>Return</v-list-item-title>
                        </v-list-item>
                    </v-list>
                    </v-menu>
                    <p><br><br>Status</p>
                </v-list-item-icon>
            </v-list-item>
        </v-list>
    </div>
</template>

<script>
    import booksList from '@/data/books.json'
    import AppHeader from '@/views/AppHeader.vue'
    export default {
        data()
        {
            return {
                books:booksList
            }
        },
        methods: {
            selectedBook()
            {   

            },
            searchInBooks(searchText)
            {
                if(searchText)
                    this.books = this.booksList.filter(rec => {return rec.title.toLowerCase().includes(searchText.toLowerCase())})
                else
                    this.books = this.booksList
            }
        },
        components: {
            AppHeader
        }
    }
</script>

<style lang="scss" scoped>

</style>