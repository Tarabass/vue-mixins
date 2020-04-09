<template>
    <v-text-field
        :counter="max"
        :rules="rules"
        :label="label"
        v-bind="$attrs"
        v-on="$listeners"
    ></v-text-field>
</template>

<script>
    import formRulesMixin from '@/mixins/formrules';

    export default {
        name: 'TextField',
        mixins: [formRulesMixin],
        props: {
            max: {
                type: Number,
                default: undefined
            },
            label: {
                type: String,
                default: 'default label'
            }
        }
    }
</script>