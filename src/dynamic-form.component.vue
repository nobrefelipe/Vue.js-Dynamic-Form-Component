<template>

    <div class="dynamic-form-group">

        <!-- TEXT INPUTS HERE -->
        <div v-for="item in form" v-if="item.type != 'group'" class="dynamic-form-group--item">

            <input :type="item.type" :value="item.value" :placeholder="item.label"/>

            <label v-if="check(item.type)"> {{ item.label }} </label>

        </div>

        <!-- CHECKBOXES AND RADIOS GROUPS HERE -->
        <div v-for="item in form" v-if="item.type == 'group'" class="dynamic-form-group--item">

            <span v-for="element in item.elements"  class="dynamic-form-group--item-sub">

                <input :type="element.type" :value="element.value" :name="element.name"/>

                <label> {{ element.label }} </label>

              </span>

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

                return ( type == 'radio' || type == 'checkbox') ? true : false;

            }

        }
    };


</script>
