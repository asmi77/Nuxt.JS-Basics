<template>
    <section class="single-recipe">
<h1>{{ recipe.title }}</h1>
<div>
    <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
</div>
<p>{{ recipe.previewText }}</p>
    </section>
</template>

<script>
    export default {
         asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
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
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
    }
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column; 
  justify-content: center;
  align-items: center;
  text-align: center; 
  padding: 30px; 
}

.recipe-image {
    width: 50%; 
}
</style>

