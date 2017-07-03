<template>

    <div class="dynamic-form-group">

        <!-- SINGLE FIELDS HERE -->
        <div v-for="item in form" v-if="item.type != 'group' && item.type != 'select'"  class="dynamic-form-group--item">

            <input :id="item.id" :type="item.type" :value="item.value" :placeholder="item.label"/>

            <label :for="item.id" v-if="check(item.type)"> {{ item.label }} </label>

        </div>

        <!-- FIELD GROUPS HERE -->
        <div v-for="item in form" v-if="item.type == 'group'" class="dynamic-form-group--item">

            <span v-for="element in item.elements"  class="dynamic-form-group--item-sub">

                <input :id="element.id" :type="element.type" :value="element.value" :name="element.name"/>

                <label :for="element.id">{{ element.label }}</label>

            </span>

        </div>

        <!-- DROPDOWNS HERE -->
        <div v-for="item in form" v-if="item.type == 'select'" class="dynamic-form-group--item">

            <label>{{ item.label }}</label>

            <select>

                <option v-for="option in item.options" :value="option.value">{{ option.name }}</option>

            </select>

        </div>

    </div>

</template>


<script>

    export default{

        name: "dynamic-form",

        props: ['form'],

        methods:{

            /*
                CHECK IF INPUT IS CHECKBOX OR RADIO SO WE DISPLAY THE LABEL
                 - use the placeholder attribute for text fields
                 - remove this control to display label for all fields
            */
            check(type){

                return ( type == 'radio' || type == 'checkbox' || type == 'select') ? true : false;

            },

        }
    };


</script>
