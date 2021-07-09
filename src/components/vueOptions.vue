<template>
    <div class="content">
        <h5 class="card-title">Vue Options Api - you have {{ getItemsCount }} item added</h5>
        <div class="input-group mb-3">
            <input 
                type="text" 
                class="form-control" 
                placeholder="Item" 
                aria-label="item" 
                aria-describedby="basic-addon2"
                @keyup.enter="addItem"
                v-model="newItem"
            >
            <div class="input-group-append">
                <button class="btn btn-outline-secondary" type="button" @click="addItem">Add</button>
            </div>
        </div>
        <ul class="list-group">
            <li 
                class="list-group-item d-flex justify-content-between align-items-center"
                v-for="(item, index) in items"
                :key="index"
                >
                <span class="badge badge-primary badge-pill">{{ item.count }}</span>
                {{ item.value }}
                <span class="badge badge-primary badge-pill" @click="deleteItem(index)">X</span>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "vueOptions",
        data () {
            return {
                newItem: "",
                items: [
                    {
                        value: "ONE",
                        count: 1
                    },
                    {
                        value: "TWO",
                        count: 1
                    },
                    {
                        value: "BLA BLA",
                        count: 1
                    }
                ]

            }
        },
        computed: {
            getItemsCount () {
                return this.items.length;
            }
        },
        methods: {
            addItem () {
                if(this.items.some(item => item.value.toLowerCase() === this.newItem.toLowerCase())){
                    let indexNewItem = this.items.findIndex(item => item.value.toLowerCase() === this.newItem.toLowerCase())
                    this.items[indexNewItem].count++
                }else{
                    this.items.push({value: this.newItem.toUpperCase(), count: 1})
                }
                this.newItem = ""
            },
            deleteItem (index) {
                this.items.splice(index, 1)
            }
        },
        watch:{
            newItem (newValue) {
                if(newValue === "dogs are better than cats"){
                    alert("shut up")
                    this.newItem = ""
                }
            }
        }
    }
</script>

<style scoped>
    h3 {
        margin: 40px 0 0;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        display: inline-block;
    }
    a {
        color: #42b983;
    }
    .content {
        width: 50%;
        margin: 0 auto;
        text-align: center;
    }
    .badge {
        color: #429e20;
    }
</style>
