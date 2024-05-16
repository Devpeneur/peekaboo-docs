---
title: Imports
sidebar_position: 1
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
<TabItem value = "js" label = "JavaScript" default>
```js
import peekaboo from '@Peekaboo/sdk';
const selected-div = some-element # your div here
const pkb = peekaboo(selected-div)
pkb.init()
```
</TabItem>
<TabItem value = "react" label = "React" default>
```js
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
```
</TabItem>

<TabItem value = "flutter" label = "Flutter" default>
```cpp
class MyHomePage extends StatelessWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);
  final String title;
 
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(title),
      ),
      // Sets the content to the
      // center of the application page
      body: const Center(
          // Sets the content of the Application
          child: Text(
        'Welcome to GeeksForGeeks!',
      )),
    );
  }
}
```
</TabItem>
</Tabs>