# Electric Eye Developer Test

## Introduction

Welcome, and congratulations!

This repository contains a fresh copy of Debut, the starter theme provided with every new Shopify store. Debut is great because it's a relatively blank slate for anyone familiar with Shopify, and is easy to understand for a neophyte.

This developer test is intentionally straight forward. It allows you to get a feel for what it's like to work with us, and us to get an idea of how you solve problems.

Try to have fun with this, and feel free to [reach out with any questions](mailto:mike@electriceye.io) you might have.

Let's get started.

## Prerequisites

Before starting, ensure you have [ThemeKit](https://shopify.github.io/themekit/), [Git](https://git-scm.com/), and a text editor like [VSCode](https://code.visualstudio.com/) installed on your machine.

You should also have a mild understanding of Shopify's [theme settings](https://shopify.dev/docs/themes/settings), [Liquid template language](https://shopify.github.io/liquid/), [Ajax API](https://shopify.dev/docs/themes/ajax-api), and are familiar with the [git workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

Finally, as this is a frontend developer role, you should be comfortable writing Javascript, CSS, and HTML.

## Setup Instructions

1. Create a [Shopify partners](https://www.shopify.com/partners) account
1. Create a [development store](https://help.shopify.com/en/partners/dashboard/managing-stores/development-stores)
1. Import the provided `products.csv`
1. Create a [private app](https://help.shopify.com/en/manual/apps/private-apps) for ThemeKit
    - Check out [this guide](https://www.shopify.com/partners/blog/95401862-3-simple-steps-for-setting-up-a-local-shopify-theme-development-environment)
1. Create a new Git repository with this code
    - Github or BitBucket preferred
    - Can be public or private
1. Create a development branch off of master
1. Complete the requirements
    - Within your dev store
    - Using the provided Debut theme (what this codebase is)
1. Review/QA code against evaluation criteria
1. Create a pull request into the master branch
1. Share link or provide access to your repo
1. Share development store URL

## Scenario

Imagine you are already on our team, and a client request comes in. They want the ability to show or hide a "buy now" button on their collection pages, allowing users to buy a product and go to checkout immediately.

Furthermore, the client would like that button to either direct the customer directly to checkout ("buy now" button), or add the product to cart and allow the customer to continue shopping. This would mimic how the add to cart button works on a product details page (PDP).

Additionally, the client would like the option to show variants for each product, allowing customers to select their variant before choosing to buy now (or add to cart based on the above setting), or direct to the specific variant on a PDP.

The additional request is deemed by the team to be out of scope for the initial build ("Phase 1"). We agree that we will only accomplish this if time allows. If not, we will push it to a "Phase 2" rollout. 

The time estimate we put on this feature is 10 hours.

## Requirements

Being mindful of the time constraint, start with completing Phase 1, and then move on to Phase 2. Each phase/step builds on the next; so try to keep your code [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

The requirements for each step/phase are as follows:

### Phase 1a

- Create a new "Collection" section in the Shopify theme customize view, under "Theme settings"
- This new setting section contains a toggle for enabling our new buy now feature
- On collection pages, a "buy now" button shows under each available product when the toggle is on
    - Do not show if the product is unavailable
- When buy now is clicked, the browser is redirected to checkout with the chosen product in the cart

### Phase 1b

- Create a second toggle to change the button to "add to cart"
- The "buy now" button under each product changes to an "add to cart" button when both toggles are on
- When add to cart is clicked, the product is added to the cart, and the browser does not redirect
- Ideally, the existing functionality for adding to cart on a PDP is replicated
    - Cart size counter in the header updates
    - A small modal displays with information about the newly added product
    - Bonus points for handling the error the same way as well

### Phase 2

- Create a third toggle to show or hide product variants
- If a product has multiple variants, a select dropdown displays
    - Each of the product's variants display as options
    - Disable variants that are unavailable
- When a different variant is selected, the data in the product listing changes
    - Image
    - Price
    - Product Link (Append Variant to URL)
- Bonus Points:
    - Always have an in-stock variant selected by default
    - Handle errors 
        - Match functionality on PDPs

## Evaluation Criteria

- Code is well organized, formatted, and documented
    - We should be able to read through your pull request and understand what's going on
    - Code is DRY
    - Spaghetti belongs in the kitchen, not in code
- Progression through the request
    - We will not "dock points" if you only accomplish one feature, however, you should at least complete Phase 1A & 1B
- Brass tacks: **does your code work?**

## Tips

When working with an existing theme, it's best to follow the established standards already in place. However, in instances where you are creating a standalone feature, your best bet is to encapsulate that feature into its own file(s). This keeps your code separate from the theme's base code, making it easier to find, modify, or remove in the future. This is usually accomplished with a [snippet](https://www.shopify.com/partners/blog/88186566-tips-for-using-snippets-in-your-shopify-theme).

More importantly, you can access global theme settings within snippets, using a [Liquid object](https://shopify.dev/docs/themes/liquid/reference/objects). You can also include  CSS `<style>` tags and JS `<script>` tags in snippets, as well as utilize Liquid objects within those tags. Your text editor might show its concerns, but it's valid, and encouraged.

~~One thing note about Debut (and many premium Shopify themes): both [jQuery](https://api.jquery.com/) and [Lodash](https://lodash.com/) are deeply integrated into it's codebase.~~

~~This is a controversial point, but I say if it's already included as part of the stack, it's fair game to use for a new feature.~~

NOTE: As of January 2021, Debut has been rewritten to exclude jQuery, Lodash, and [Slate](https://shopify.github.io/slate/docs/about). **This version of debut (16.7.1) has these libraries.**

This provides an interesting conundrum: To use the libraries or not to use. Write your code faster but with no support for new versions of the theme. Or, spend the time to write this code "vanilla" and ensure compatibility. Pick your poison.

## Parting Thoughts

Remember that everyone works a little differently, and there truly is no right answer to any one problem. The way you solve a problem today, might not be how you'd do it the next time around. Be kind to yourself; don't get lost in finding the perfect solution, and forget to come up with one at all. As a Great Programming Sage once said: **_"Today's code is tomorrow's trash"_**.

Happy coding! -MW
