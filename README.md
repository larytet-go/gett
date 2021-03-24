# gett

``
// brute force : genetrate all posible tuples sum of which is 24 compleixty O(n^3)
// If the data is sortedis can be done in O(n^2) by checking pairs against the third number
type tuple struct {
    a int 
    b int
    c int
}
```



```
func isValid(i, j, k int, data []int) bool {
  return (data[i]+data[j]+data[k]) == 24
}

 func checkTuple(data []int) {
  result := []tuple{}
  l := len(data)
 	for i := 0;i < l;i++ {
    for j := 0;j < l;j++ {
      if j == i {
         continue
      }
    	if !thereIsChance(i, j) {
      	continue
      }
      for k := 0;k < l;k++ {
          if j == i || k == i {
             continue
          }
          if isValid(i, j, k, data) {
          	result = append(result, tuple{data[i], data[j], data[k]})
          }
      }
    }
  }
  fmt.Print("%v", result)
 }
 ```
