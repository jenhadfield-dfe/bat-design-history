---js
{
  layout: "user-needs",
  description: "User needs for Publish teacher training courses",
  permalink: "publish-teacher-training-courses/user-needs/{% if pagination.pageNumber > 0 %}page/{{ pagination.pageNumber + 1 }}{% else %}index{% endif %}.html",
  eleventyComputed: {
    title: "User needs for Publish",
    eleventyNavigation: {
      key: data => data.title,
      parent: "Publish teacher training courses"
    }
  }
}
---
