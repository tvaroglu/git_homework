```
Pseudo-code practice exercise for a function to count the number of sheep in the barn

1.)  name the variables (assumptions/givens)
  true = sheep
  false = piglet
  sheepCounter = 0

2.)  define outcomes
  if 0 true = oink oink
  if 1 true = is 1 sheep
  if 2+ true = ARE {sheepCounter} sheep

3.)  arrive at outcome
  look in the barn
    for all animals in the barn, if animal is true
      count 1 sheep
    (until no more animals to count)

4.)   return outcome as applicable (per step 2)
```

```ruby
# Actual function call
def countSheep(barn)
	# true == "sheep"
	# false == "piglet"
	sheepCount = 0

	for animal in barn do
		if animal == true then
			sheepCount += 1
		end
	end

	if sheepCount == 0 then
		prompt = "Oink oink, no sheep here!"
	elsif sheepCount == 1 then
		prompt = "There is 1 sheep in the barn!"
	elsif sheepCount > 1 then
		prompt = "There are #{sheepCount} sheep in the barn!"
	end

	return prompt
end


# Test suite
def assertEquals(actual, expected, testName)
	if actual = expected then
		puts "passed '#{testName}': expected '#{expected}', and got '#{actual}'"
	else
		puts "failed '#{testName}': expected '#{expected}', but got '#{actual}'"
	end
end

# Test for no sheep
assertEquals(countSheep([false, false, false, false]), "Oink oink, no sheep here!", "it correctly returns the prompt when no sheep are in the barn")
# Test for one sheep
assertEquals(countSheep([false, false, true, false]), "There is 1 sheep in the barn!", "it correctly returns the prompt when one sheep is in the barn")
# Test for more than one sheep
assertEquals(countSheep([false, true, true, false]), "There are 2 sheep in the barn!", "it correctly returns the prompt when more than one sheep is in the barn")
```
