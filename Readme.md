##React calls a fuction again and again when a variable changes
##clean up function

- useEffect
  (function() {
  console.log("on mount")
  let clock = setInterval(function() {
  console.log("from inside setInterval")
  setCount(c => c + 1)
  }, 1000)
  //this is clean up function
  return function() {
  console.log("on unmount")
  clearInterval(clock)
  }
  }, [])
