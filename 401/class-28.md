# RecyclerView
- You supply the data and define how each item looks, and the RecyclerView library dynamically creates the elements when they're needed. As the name implies, RecyclerView recycles those individual elements. When an item scrolls off the screen, RecyclerView doesn't destroy its view. Instead, RecyclerView reuses the view for new items that have scrolled onscreen.

## Key classes
- RecyclerView is the ViewGroup that contains the views corresponding to your data. 

- Each individual element in the list is defined by a view holder object. When the view holder is created, it doesn't have any data associated with it.

- The RecyclerView requests those views, and binds the views to their data, by calling methods in the adapter. You define the adapter by extending RecyclerView.Adapter.

- The layout manager arranges the individual elements in your list. You can use one of the layout managers provided by the RecyclerView library, or you can define your own.

## Steps for implementing your RecyclerView
- If you're going to use RecyclerView, there are a few things you need to do. They'll be discussed in detail in the following sections
    - First of all, you have install RecyclerView library 

    - Design how each element in the list is going to look and behave. Based on this design, extend the ViewHolder class.

    - Define the Adapter that associates your data with the ViewHolder views.


## Plan your layout
- The items in your RecyclerView are arranged by a LayoutManager class.
    1. LinearLayoutManager
    2. GridLayoutManager
    3. StaggeredGridLayoutManager

## Implementing your adapter and view holder
- Once you determined your layout, you need to implement your Adapter and ViewHolder. The ViewHolder is a wrapper around a View that contains the layout for an individual item in the list. The process of associating views to their data is called binding.
- When you define your adapter, you need to override three key methods
    1. onCreateViewHolder()
    2. onBindViewHolder()
    3. getItemCount()
