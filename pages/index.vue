<script setup lang="ts">
const selectedDayOfWeek = ref([0, 1, 2, 3, 4, 5])
const flagHoliday = ref(true)

const weekDays = [
    {
        "key": 0,
        "day": "Monday",
    },
    {
        "key": 1,
        "day": "Tuesday",
    },
    {
        "key": 2,
        "day": "Wednesday",
    },
    {
        "key": 3,
        "day": "Thursday",
    },
    {
        "key": 4,
        "day": "Friday",
    },
    {
        "key": 5,
        "day": "Saturday",
    },
    {
        "key": 6,
        "day": "Sunday",
    }
]

const projectPanel = ref([0, 1])

</script>

<template>
    <v-expansion-panels
        v-model="projectPanel"
        variant="accordion"
        multiple
    >
        <!-- Project Info Panel -->
        <v-expansion-panel>
            <v-expansion-panel-title>
                Project Info
            </v-expansion-panel-title>
            <v-expansion-panel-text>
                <v-container>
                    <v-row>
                        <v-col
                            cols="12"
                            sm="6"
                        >
                            <v-text-field
                                label="Start date"
                                type="date"
                            />
                        </v-col>

                        <v-col
                            cols="12"
                            sm="6"    
                        >
                            <v-text-field
                                label="End date"
                                type="date"
                            />
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col
                            cols="24"
                            sm="12"
                        >
                            <v-select
                                v-model="selectedDayOfWeek"
                                label="Business day"
                                :items="weekDays"
                                item-title="day"
                                item-value="key"
                                clearable
                                multiple
                            ></v-select>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col>
                            <v-checkbox
                                v-model="flagHoliday"
                                label="Holiday"
                            ></v-checkbox>
                        </v-col>
                    </v-row>
                </v-container>
            </v-expansion-panel-text>
        </v-expansion-panel>
        
        <!-- Project Info Panel -->
        <v-expansion-panel>
            <v-expansion-panel-title>
                Member Info
            </v-expansion-panel-title>
            <v-expansion-panel-text>
                <v-container>
                    <!-- TODO: 動的にコンポーネント追加できるようにする -->
                    <v-row>
                        <v-col
                            cols="12"
                            sm="6"
                        >
                            <v-text-field
                                label="Worker"
                            />
                        </v-col>

                        <v-col
                            cols="12"
                            sm="3"    
                        >
                            <v-text-field
                                label="Rate"
                                model-value=100
                                type="number"
                                suffix="%"
                            />
                        </v-col>
                    </v-row>
                </v-container>
            </v-expansion-panel-text>
        </v-expansion-panel>

        <!-- Tasks Panel -->
        <v-expansion-panel>
            <v-expansion-panel-title>
                Tasks
            </v-expansion-panel-title>
            <v-expansion-panel-text>
                <v-container>
                    <!-- TODO: 動的にコンポーネント追加できるようにする -->
                    <v-row>
                        <v-col
                            cols="12"
                            sm="6"
                        >
                            <v-text-field
                                label="Task"
                            />
                        </v-col>

                        <v-col
                            cols="12"
                            sm="1"
                        >
                            <v-text-field
                                label="Day"
                                model-value=1
                                type="number"
                            />
                        </v-col>
                        <v-col
                            cols="12"
                            sm="5"
                        >
                            <v-select
                                label="Dependencies"
                                clearable
                                multiple
                            />
                        </v-col>
                    </v-row>
                </v-container>
            </v-expansion-panel-text>
        </v-expansion-panel>
    </v-expansion-panels>
</template>