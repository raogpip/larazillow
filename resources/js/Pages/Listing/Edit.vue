<template>
    <form @submit.prevent="update">
        <div class="grid grid-cols-6 gap-4">
            <div class="col-span-2">
                <label class="label">Beds</label>
                <input class="input" type="text" v-model.number="form.beds" />
                <ErrorMessage
                    v-if="form.errors.beds"
                    :error="form.errors.beds"
                />
            </div>

            <div class="col-span-2">
                <label class="label">Baths</label>
                <input class="input" type="text" v-model.number="form.baths" />
                <ErrorMessage
                    v-if="form.errors.baths"
                    :error="form.errors.baths"
                />
            </div>

            <div class="col-span-2">
                <label class="label">Area</label>
                <input class="input" type="text" v-model.number="form.area" />
                <ErrorMessage
                    v-if="form.errors.area"
                    :error="form.errors.area"
                />
            </div>

            <div class="col-span-4">
                <label class="label">City</label>
                <input type="text" class="input" v-model="form.city" />
                <ErrorMessage
                    v-if="form.errors.city"
                    :error="form.errors.city"
                />
            </div>

            <div class="col-span-2">
                <label class="label">Post Code</label>
                <input class="input" type="text" v-model="form.code" />
                <ErrorMessage
                    v-if="form.errors.code"
                    :error="form.errors.code"
                />
            </div>

            <div class="col-span-4">
                <label class="label">Street</label>
                <input class="input" type="text" v-model="form.street" />
                <ErrorMessage
                    v-if="form.errors.street"
                    :error="form.errors.street"
                />
            </div>

            <div class="col-span-2">
                <label class="label">Street Nr</label>
                <input
                    class="input"
                    type="text"
                    v-model.number="form.street_nr"
                />
                <ErrorMessage
                    v-if="form.errors.street_nr"
                    :error="form.errors.street_nr"
                />
            </div>

            <div class="col-span-6">
                <label class="label">Price</label>
                <input class="input" type="text" v-model.number="form.price" />
                <ErrorMessage
                    v-if="form.errors.price"
                    :error="form.errors.price"
                />
            </div>

            <div class="col-span-6">
                <button type="submit" class="btn-primary">Edit</button>
            </div>
        </div>
    </form>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";
import ErrorMessage from "@/Components/ErrorMessage.vue";

const props = defineProps({
    listing: Object,
});

const form = useForm({
    beds: props.listing.beds,
    baths: props.listing.baths,
    area: props.listing.area,
    city: props.listing.city,
    code: props.listing.code,
    street: props.listing.street,
    street_nr: props.listing.street_nr,
    price: props.listing.price,
});

const update = () =>
    form.put(route("listing.update", { listing: props.listing.id }));
</script>

<style scoped>
label {
    margin-right: 2em;
}

div {
    padding: 2px;
}
</style>
