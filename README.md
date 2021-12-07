# ListView with Dynamic Data

This example implements the common use case of displaying a ListView using a dynamic set of data from an external source. 


For this example the data is provided by a method called `getMockItems` which includes static data but could just as easily be dynamic data from an API or other data source. 

```dart
List<Item> getMockItems() {
    return [
      Item(name: "name", text: "text"),
      Item(name: "name", text: "text"),
      Item(name: "name", text: "text"),
      Item(name: "name", text: "text"),
      Item(name: "name", text: "text"),
      Item(name: "name", text: "text"),
    ];
  }
```

To use the ListView in this model you'll use the length of the List for `itemCount:`. Next, `itemBuilder:` is called for each entry in the list when it's time to display it. In this example, the index is provided to a function called `buildListItem` which returns the view of a single entry. 



```dart
List<Item> items = getMockItems();

...

body: ListView.builder(
        itemCount: items.length,
        itemBuilder: (BuildContext ctxt, int index) {
          return buildListItem(items[index]);
        },
      ),
```

