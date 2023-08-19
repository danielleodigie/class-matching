<script setup>
import { allRows } from '@/composables/useSheet';
import FaceCard from '../components/FaceCard.vue';
import SearchInput from '../components/SearchInput.vue';

const headings = ref(null)
const result = ref([])
const { data } = await allRows()

headings.value = data.value.values[0]
result.value = [...data.value.values]
result.value.splice(0, 1)
const searchQuery = ref('');
const filteredResults = computed(() => {
  const query = searchQuery.value.toLowerCase(); // Convert the search query to lowercase
  return result.value.filter(entry => {
    // Convert the classes to lowercase before checking if they include the search query
    return entry[4].split(', ').some(classItem => classItem.toLowerCase().includes(query));
  });
});
</script>

<template>
    <div class="container">
        
        <div id="classwelcome">
            <h1>Meet your Classmates</h1>
            <p>Looking for people in a particular class? Search by class (i.e. "COMS 1004", "coms", "1004")</p>
            <SearchInput v-model:value="searchQuery" ></SearchInput>
        </div>
        <div id="classcontainer">
            <span v-for="entry in filteredResults "> <FaceCard :name="entry[0]" :uni="entry[1]" :email="entry[2]" :phone="entry[3]" :classes="entry[4].split(', ')" ></FaceCard></span>
            <div v-if="filteredResults.length === 0" class="no-results">
                <p>No results found</p>
            </div>
        </div>     
        
    </div>
</template>


<style>

#classwelcome{
    width: 30%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    font-family: Montserrat;
    color: #233a60;
    text-align: center;
}


.container {
    display: flex;
    justify-content: space-around;
    flex-direction: row;
    height: 100%;
}

#classcontainer{
    margin-top: 30px;
    width: 60%;
    max-height: 750px;
    overflow: auto;
    display: flex;
    flex-wrap: wrap;
    border-radius: 13px;
    background: #d1dff6;
    box-shadow:  inset 7px 7px 14px #b0bbcf,
                inset -7px -7px 14px #f2ffff;
    align-items: center;
    justify-content: center;

}

body{
    background-color: #d1dff6;
}

.no-results{
    font-family: Montserrat;
}

@media only screen and (max-width: 768px) {
        .container{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        #classcontainer{
            width: 95%;
        }

        #classwelcome{
            width: 75%;
        }

    }
</style>