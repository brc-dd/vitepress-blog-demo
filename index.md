# Latest posts

<div v-for="article in articles">

<h2><a :href="article.path">{{ article.title }}</a></h2>

{{ article.excerpt }}

**~ {{ article.Author }}** ({{ transformDate(article.Updated) }})

</div>

<script setup>
import data from './data.json'

// sort articles
const articles = data.sort(
  (a, b) => new Date(b.Updated) - new Date(a.Updated)
)

const transformDate = (date) =>
  new Date(date).toLocaleDateString('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric'
  })
</script>
