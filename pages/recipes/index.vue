<template>
    <section class="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key="recipe.id"
        :thumbnail="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText"
        />
    </section>
</template>
<script>
import Recipe from "@/components/Recipe";

export default {
  components: {
    Recipe
  },
  asyncData() {
    // if using a request
    // return axios.get()
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Melba strawberries",
              previewText: "Fabulous desert",
              thumbnail:
                "https://img.taste.com.au/uHDkf_kl/taste/2016/11/peach-melba-with-whipped-ricotta-cream-92563-1.jpeg"
            },
            {
              id: "2",
              title: "Sea food",
              previewText: "Tasty diet",
              thumbnail:
                "https://www.iheartnaptime.net/wp-content/uploads/2016/03/Easy-and-Delicious-Slow-Cooker-Seafood-Stew-Recipe-.jpg"
            },
            {
              id: "3",
              title: "Magic Spoon",
              previewText: "The icing on the cake",
              thumbnail:
                "https://i.pinimg.com/736x/8d/8e/21/8d8e212154e453cf6ba323728318acf8--vintage-silver-antique-silver.jpg"
            }
          ]
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>

