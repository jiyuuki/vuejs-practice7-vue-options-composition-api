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
    import { ref, computed, watch } from "vue"
    export default {
        setup () {
            let newItem = ref("")
            let items = ref([
                {
                    value: "One",
                    count: 1
                },
                {
                    value: "Two",
                    count: 1
                },
                {
                    value: "Three",
                    count: 1
                }
            ])
            let addItem = () => {
                if(items.value.some(item => item.value === newItem.value)){
                    let indexNewItem = items.value.findIndex(item => item.value === newItem.value)
                    items.value[indexNewItem].count++
                }else{
                    items.value.push({value: newItem.value, count: 1})
                }
                newItem.value = ""; 
            }
            let deleteItem = (index) => {
                items.value.splice(index, 1)
            }

            let getItemsCount = computed(() => {
                return items.value.length
            })

            watch(newItem, (newValue) => {
                if(newValue === "dogs are better than cats"){
                    alert("shut up")
                }
            })

            return {
                // Data
                newItem,
                items,

                // Methods
                addItem,
                deleteItem,

                // Computed
                getItemsCount,
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
