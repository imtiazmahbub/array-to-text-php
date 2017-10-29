# Array to Text Table
*forked from https://gist.github.com/tony-landis/31477*

This PHP class can convert an array into ascii text table.

## Example Usage:

```
require_once ('ArrayToTextTable.php');

$data = array(
	array('company'=>'AIG', 'id'=>1, 'balance'=> '-$99,999,999,999.00'),
	array('company'=>'Wachovia', 'id'=>2, 'balance'=> '-$10,000,000.00'),
	array('company'=>'HP', 'id'=>3, 'balance'=> '$555,000.000.00'),
	array('company'=>'IBM', 'id'=>4, 'balance'=> '$12,000.00')
);

$renderer = new ArrayToTextTable($data);
$renderer->showHeaders(true);
$renderer->render();
```
### Output of above example
```
+----------+----+---------------------+
| COMPANY  | ID |       BALANCE       |
+----------+----+---------------------+
| AIG      | 1  | -$99,999,999,999.00 |
| Wachovia | 2  | -$10,000,000.00     |
| HP       | 3  | $555,000.000.00     |
| IBM      | 4  | $12,000.00          |
+----------+----+---------------------+
```


## Useful Methods:

#### `render` *default: false*
You can catch the output of the render with `render(true)`
```
$output = $renderer->render(true);
```

#### `showHeaders` *default: false*
Show the headers using the key values of the array for the titles
```
$renderer->showHeaders(true);
```

#### `setMaxWidth` *default: 30*
Set the maximum width (number of characters) per column before truncating
```
$renderer->setMaxWidth(30);
```

#### `setMaxHeight` *default: 2*
Set the maximum height (number of lines) per row before truncating
```
$renderer->setMaxHeight(30);
```
