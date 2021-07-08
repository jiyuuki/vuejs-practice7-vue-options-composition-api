<template>
    <div class="content">
        <h5 class="card-title">Vue options - you have {{ itemsCount }} item added</h5>
        <div class="input-group mb-3">
            <input 
                type="text" 
                class="form-control" 
                placeholder="Item" a
                ria-label="item" 
                aria-describedby="basic-addon2"
                @keyup.enter="addItem"
            >
            <div class="input-group-append">
                <button class="btn btn-outline-secondary" type="button" @click="addItem">Add</button>
            </div>
        </div>
        <ul class="list-group">
            <li class="list-group-item d-flex justify-content-between align-items-center">
                <span class="badge badge-primary badge-pill">{{ itemCount }}</span>
                Cras justo odio
                <span class="badge badge-primary badge-pill" @click="deleteItem">X</span>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'vueOptions',
    data () {
        return {
            itemsCount: 0,
            itemCount: 1,

        }
    },
    methods: {
        addItem () {
            console.log('addItem')
        },
        deleteItem () {
            console.log('deleteItem')
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
