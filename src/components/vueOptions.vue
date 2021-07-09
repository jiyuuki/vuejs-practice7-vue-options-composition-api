<template>
    <div class="content">
        <h5 class="card-title">Vue options - you have {{ getItemsCount }} item added</h5>
        <div class="input-group mb-3">
            <input 
                type="text" 
                class="form-control" 
                placeholder="Item" a
                ria-label="item" 
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
            itemsCount: 0,
            itemCount: 1,
            newItem: "",
            items: [
                {
                    value: "One",
                    count: 1
                },
                {
                    value: "Two",
                    count: 1
                },
                {
                    value: "bla bla",
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
            if(this.items.some(item => item.value === this.newItem)){
                let indexNewItem = this.items.findIndex(item => item.value === this.newItem)
                this.items[indexNewItem].count++
            }else{
                this.items.push({value: this.newItem, count: 1})
            }
            this.newItem = ""; 
        },
        deleteItem (index) {
            this.items.splice(index, 1)
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
