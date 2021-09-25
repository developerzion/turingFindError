## **Turing Challenge: findError using PHP**

```php
class Solution
{	
	function findError($num)
	{	

		$array = array();

		$unique = array_unique($num);
		$duplicate = array_diff_assoc($num, $unique);
		if($duplicate){
			foreach ($duplicate as $key=>$dup) {
				array_push($array, $dup);
				$value = $key + 1;
				array_push($array, $value);
			}			
		}
		return $array;	
	}
}

$nums = [1,2,2];
$solution = new Solution();
$output = $solution->findError($nums);
echo '['.implode(",", $output).']';
```
```php
Output: [2,3]
```