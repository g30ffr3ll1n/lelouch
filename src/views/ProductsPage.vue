<template>
    <NavComponent>
        <div class="h-full w-full flex flex-col py-8">
            <div class="h-full w-full flex">
                <div class="h-full xl:w-1/2 2xs:w-full flex flex-col mt-12">
                    <div class="flex justify-between">
                        <p class="md:text-6xl 2xs:text-2xl font-bold">Products</p>
                        <div class="pl-6">
                            <input id="search" v-model="search" name="username" type="text" required=""
                                class="relative block md:w-72 md:h-14 2xs:w-40 2xs:h-10 appearance-none rounded-md border border-black focus:border-black px-3 py-2 text-[#636262] placeholder-[#c4c4c4] focus:outline-none lg:text-xl 2xs:text-sm focus:ring-0"
                                placeholder="Search for keyword..." />
                        </div>
                    </div>
                </div>
            </div>
            <div class="h-full w-full flex xl:flex-row 2xs:flex-col">
                <div class="h-full xl:w-1/2 2xs:w-full flex flex-col mt-12">

                    <EasyDataTable :headers="headers" :items="items" :search-value="search" border-cell hide-footer
                        table-class-name="customize-table" header-text-direction="center" body-text-direction="center">
                        <template #item-operation="item">
                            <div class="operation-wrapper flex justify-center py-1 space-x-2">
                                <button class="flex rounded-lg bg-black text-gray-200 text-lg px-4 py-1 font-semibold"
                                    @click="editItem(item)">
                                    Edit
                                </button>
                                <button
                                    class="flex rounded-lg bg-white text-black border-2 border-black text-lg px-4 py-1 font-semibold"
                                    @click="deleteItem(item)">
                                    Delete
                                </button>
                            </div>
                        </template>
                    </EasyDataTable>

                </div>
                <div class="xl:w-1/2 2xs:w-full px-12 mt-12">
                    <div class="flex flex-col bg-[#ececec] items-center justify-center p-14">
                        <p class="text-3xl font-bold text-center">Header Text</p>
                        <p class="text-[#636262] mt-4 text-2xl font-medium px-12 text-center">Add or Create a Product
                            Lorem
                            ipsum dolor sit amet
                        </p>
                        <div class="flex flex-col mt-16 w-full space-y-8">
                            <input id="search" v-model="name" name="name" type="text" required=""
                                class="relative block w-full h-14 appearance-none rounded-md border-none px-3 py-2 text-[#636262] placeholder-[#c4c4c4] focus:outline-none lg:text-xl 2xs:text-sm focus:ring-0"
                                placeholder="Name" />
                            <input id="search" v-model="price" name="price" type="text" required=""
                                class="relative block w-full h-14 appearance-none rounded-md border-none px-3 py-2 text-[#636262] placeholder-[#c4c4c4] focus:outline-none lg:text-xl 2xs:text-sm focus:ring-0"
                                placeholder="Price" />
                        </div>
                        <button
                            class="flex w-full justify-center rounded-lg bg-black text-gray-200 px-6 py-3 mt-8 text-xl font-semibold"
                            @click="editing ? saveEdit() : addItem()">
                            {{ editing? "Save": "Create" }}
                        </button>
                    </div>
                </div>
            </div>

        </div>

    </NavComponent>
</template>

<script>
import NavComponent from '@/components/NavComponent.vue';

export default {
    name: 'ProductsPage',
    components: {
        NavComponent,
        EasyDataTable: window['vue3-easy-data-table'],
    },
    data: () => ({
        search: "",
        name: "",
        price: "",
        editing: false,
        headers: [
            { text: "Name", value: "name", width: 150 },
            { text: "Price", value: "price", width: 150 },
            { text: "Operation", value: "operation", width: 150 },
        ],
        items: [
            { id: 1, name: "name1", price: "price1", },
            { id: 2, name: "name2", price: "price2", },
            { id: 3, name: "name3", price: "price3", },
            { id: 4, name: "name4", price: "price4", },
            { id: 5, name: "name5", price: "price5", },
            { id: 6, name: "name6", price: "price6", },
            { id: 7, name: "name7", price: "price7", },
        ],
        editingItem: {
            name: "",
            price: "",
            id: 0,
        }
    }),
    methods: {
        addItem() {
            const item = {
                id: Math.floor(Math.random() * 9999 + 1),
                name: this.name,
                price: this.price,
            }
            this.items.push(item);
            this.name = ""
            this.price = ""
        },
        editItem(chosenItem) {
            console.log(chosenItem);
            this.editing = true;
            this.editingItem = chosenItem;
            this.name = chosenItem.name;
            this.price = chosenItem.price;
            console.log(this.editingItem);
        },
        saveEdit() {
            this.items = this.items.map(item => {
                if (item.id === this.editingItem.id) {
                    item.name = this.name;
                    item.price = this.price;
                }
                return item;
            })
            this.name = ""
            this.price = ""
            this.editing = false;
        },
        deleteItem(chosenItem) {
            this.items = this.items.filter((item) => item.id !== chosenItem.id);
        }
    },
}
</script>

<style>
.customize-table {
    --easy-table-border: 1px solid black;
    --easy-table-row-border: 1px solid black;

    --easy-table-header-font-size: 1.5rem;
    --easy-table-header-height: 4rem;
    --easy-table-header-background-color: #ececec;

    --easy-table-body-row-font-color: #9d9d9d;
    --easy-table-body-row-height: 4.5rem;
    --easy-table-body-row-font-size: 1.5rem;

}
</style>