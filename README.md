# Display Posts Shortcode #

- **Contributors:** daniftodi
- **Donate link:** https://paypal.me/diftodi
- **Tags:** shortcode, pages, posts, page, query, display, list, timeline
- **Requires at least:** 3.0
- **Tested up to:** 4.8

Display a posts timeline

## Description ##

The *WP Timeline* was written to allow users to easily display timelines of posts without knowing PHP or editing template files.

Add the shortcode in a post or page, and use the arguments to query based on tag, category, post type, and many other possibilities. You can also customize the output with parameters like: include_date, include_excerpt, and image_size.

* [Available Parameters](https://github.com/daniftodi/wp-timeline/blob/master/README.md#parameters)
* [Customization with Filters](https://github.com/daniftodi/wp-timeline/wiki#customization-with-filters)
* [Extension Plugins](https://github.com/daniftodi/wp-timline/wiki#extension-plugins)
* [Full Change Log](https://github.com/daniftodi/wp-timeline/blob/master/CHANGELOG.md)
* [View on GitHub](https://github.com/daniftodi/wp-timeline)

== Installation ==

1. Upload `di-timeline` to the `/wp-content/plugins/` directory.
1. Activate the plugin through the *Plugins* menu in WordPress.
1. Add the shortcode to a post or page.

## Parameters ##

**author**
Specify the post author.
Default: empty
Example: [wp-timeline author="bill"]

**category**
Specify the category slug, or comma separated list of category slugs.
Default: empty
Example: [wp-timeline category="fishing,hiking"]

**category_id**
Specify the category ID  
Default: empty  
Example: [wp-timeline category_id="123"]

**category_display**
Specify 'true' to display the categories the current post is in. Specify a taxonomy slug (e.g., 'post_tag') to list a different taxonomy.
Default: empty
Example: [wp-timeline category_display="true"]

**category_label**
If using category_display, specify the label that appears before the list of categories.
Default: "Posted in: "
Example: [wp-timeline category_display="true" category_label="Categorized as: "]

**content_class**
Specify the class name used for the post content.
Default: content
Example: [wp-timeline include_content="true" content_class="dps-listing-content"]

**date_format**
Specify the date format used when 'include_date' or 'include_date_modified' is true. See [Formatting Date and Time](http://codex.wordpress.org/Formatting_Date_and_Time) on the Codex for more information.
Default: '(n/j/Y)'
Example: [wp-timeline include_date="true" date_format="F j, Y"]

**date**
Specify a date to query for posts published that date. [More info on Date Queries](https://github.com/billerickson/display-posts-shortcode/wiki#date-queries).
Default: empty
Example: [wp-timeline date="2014-09-07"]

**date_column**
Specify which date column to use for all date queries. [More info on Date Queries](https://github.com/billerickson/display-posts-shortcode/wiki#date-queries).
Default: post_date
Example: [wp-timeline date="Yesterday" date_column="post_modified_date"]

**date_compare**
Specify the comparison operator used for all date queries. [More info on Date Queries](https://github.com/billerickson/display-posts-shortcode/wiki#date-queries).
Default: =
Example: [wp-timeline date="-1 year" date_compare=">"]

**date_query_before**
Specify the before argument for a date query. [More info on Date Queries](https://github.com/billerickson/display-posts-shortcode/wiki#date-queries).
Default: empty
Example: [wp-timeline date_query_before="2015-12-31" date_query_after="2015-01-01"]

**date_query_after**
Specify the after argument for a date query. [More info on Date Queries](h/wiki#date-queries).
Default: empty
Example: [wp-timeline date_query_before="2015-12-31" date_query_after="2015-01-01"]

**date_query_column**
Specify the date column used for this query. [More info on Date Queries](https://github.com/daniftodi/wp-timeline/wiki#date-queries).
Default: post_date
Example: [wp-timeline date="Yesterday" date_query_column="post_modified_date"]

**date_query_compare**
Specify the comparison operator used for this query. [More info on Date Queries](https://github.com/daniftodi/wp-timeline/wiki#date-queries).
Default: =
Example: [wp-timeline date="-1 year" date_query_compare=">"]

**excerpt_length**
Specify the number of words used in an excerpt. [More information](https://github.com/daniftodi/wp-timeline/issues/110).
Default: empty (set by your theme)
Example: [wp-timeline include_excerpt="true" excerpt_length="20"]

**excerpt_more**
Specify the more text that appears after the excerpt.
Default: empty (set by your theme)
Example: [wp-timeline include_excerpt="true" excerpt_more="..."]

**excerpt_more_link**
Specify whether or not to link the excerpt_more text to the post.
Default: false
Example: [wp-timeline include_excerpt="true" excerpt_more="Continue Reading" excerpt_more_link="true"]

**exclude**
Specify one or more post IDs to exclude from query  
Default: false  
Example: [wp-timeline exclude="9, 11"]

**exclude_current**
Specify whether or not to exclude the current post from the query  
Default: false  
Example: [wp-timeline exclude_current="true" taxonomy="category" tax_term="current"]

**id**
Specify a specific post ID (or multiple post IDs) to display.
Default: empty
Example: [wp-timeline id="9, 10"]

**ignore_sticky_posts**
Specify whether or not to ignore sticky posts.
Default: false
Example: [wp-timeline ignore_sticky_posts="true"]

**image_size**
Specify an image size for displaying the featured image, if the post has one. The image_size can be set to thumbnail, medium, large (all controlled from Settings > Media), or a [custom image size](https://developer.wordpress.org/reference/functions/add_image_size/). See [Image Alignment](https://github.com/daniftodi/wp-timeline/wiki#image-alignment)
Default: empty
Example: [wp-timeline image_size="thumbnail"]

**include_author**
Specify whether or not to include the post's author name.
Default: false
Example: [wp-timeline include_author="true"]

**include_content**
Specify whether or not to include the full post content. Note that [wp-timeline] will be stripped out of the content to prevent infinite loops
Default: false
Example:[wp-timeline include_content="true"]

**include_date**
Include the post's date after the post title. The default format is (7/30/12), but this can be customized using the 'date_format' parameter.
Default: empty
Example [wp-timeline include_date="true"]

**include_date_modified**
Include the post's last modified date after the post title. The default format is (7/30/12), but this can be customized using the 'date_format' parameter. Note that this can only be used if 'include_date' is not true.
Default: empty
Example [wp-timeline include_date_modified="true"]

**include_excerpt**
Include the post's excerpt after the title (and date if provided).
Default: empty
Example: [wp-timeline include_excerpt="true"]

**include_title**
Include the post's title.
Default: true
Example: [wp-timeline include_title="false" image_size="thumbnail"]

**include_link**
Post's title is link to post page.
Default: true
Example: [wp-timeline include_title="true" include_link="false"]

**meta_key**
Specify a meta key, for meta queries or ordering.
Default: empty
Example: [wp-timeline meta_key="price" orderby="meta_value_num" order="ASC"]

**meta_value**
Specify a meta value, for meta queries.
Default: empty
Example: [wp-timeline meta_key="color" meta_value="blue"]

**no_posts_message**
Specify a message to display if no posts are found.
Default: empty
Example: [wp-timeline category="on-sale" no_posts_message="Sorry, no items are currently on sale"]

**offset**
The number of posts to pass over.
Default: 0
Example: [wp-timeline offset="3"]

**order**
Specify whether posts are ordered in descending order (DESC) or ascending order (ASC).
Default: DESC
Example: [wp-timeline order="ASC"]

**orderby**
Specify what the posts are ordered by. See the available parameters [here](http://codex.wordpress.org/Class_Reference/WP_Query#Order_.26_Orderby_Parameters).
Default: date
Example: [wp-timeline orderby="title"]

**post_parent**
Display the pages that are a child of a certain page. You can either specify an ID or 'current', which displays the children of the current page.
Default: empty
Example: [wp-timeline post_type="page" post_parent="8"]

**post_status**
Show posts associated with a certain [post status](http://codex.wordpress.org/Class_Reference/WP_Query#Status_Parameters).
Default: publish
Example: [wp-timeline post_status="publish, future"]

**post_type**
Specify which post type to use. You can use a default one (post or page), or a custom post type you've created.
Default: post
Example: [wp-timeline post_type="event"]

**posts_per_page**
How many posts to display.
Default: 10
Example: [wp-timeline posts_per_page="5"]

**tag**
Display posts from a specific tag, or tags. You must use the tag slug(ex: example-tag), not the tag's name (ex: Example Tag).
Default: empty
Example: [wp-timeline tag="tag1, tag2"]

**taxonomy, tax_term, and tax_operator**
Use these parameters to do [advanced taxonomy queries](http://codex.wordpress.org/Class_Reference/WP_Query#Taxonomy_Parameters). Use 'taxonomy' for the taxonomy you'd like to query, 'tax_term' for the term slug (or terms) you'd like to include, and 'operator' to change how the query uses those terms (most likely this field will not be needed). See [Multiple Taxonomy Queries](https://github.com/daniftodi/wp-timeline/wiki#multiple-taxonomy-queries).
Default: 'taxonomy' = empty , 'tax_term' = empty , 'tax_operator' = 'IN'
Example: [wp-timeline taxonomy="color" tax_term="blue, green"]

**time**
Specify the time, to be used in a date query. [More info on Date Queries](https://github.com/daniftodi/wp-timeline/wiki#date-queries).
Default: empty
Example: [wp-timeline date="Yesterday" time="9:00am"]

**title**
Give the list of posts a title heading.
Default: empty
Example: [wp-timeline title="Recent Posts"]

**wrapper**
What type of HTML should be used to display the listings. It can be an unordered list (ul), ordered list (ol), or divs (div) which you can then style yourself.
Default: ul
Example: [wp-timeline wrapper="ol"]

**wrapper_class**
Class applied to the wrapper tag for custom css formatting for this instance.
Default: display-posts-listing
Example: [wp-timeline wrapper="div" wrapper_class="my-grid-layout"]

**wrapper_id**
Specify an unique ID to be used on the wrapper of this listing.
Default: empty
Example: [wp-timeline category="cars" wrapper_id="cars-listing"]

