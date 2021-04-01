```
PseudoCode practice: Data Normalization

method first_name_vs_last_name_cleanup(array_of_input_strings)
  # create output array variable
  # iterate over the array_of_input_strings
    # for each string in the input array
      # split string on '_'
      # assign left side of string split (index 0) as new variable
        # uppercase the first character of this string variable
          # look at index 0 (first character of string), apply upcase method
      # assign right side of string split (index 1) as new variable
        # uppercase the first character of this string variable
          # look at index 0 (first character of string), apply upcase method
      # interpolate "#{Firstname} #{Lastname}" as new string variable
      # add interpolated string variable to output array
  # return output array
```

```ruby
# Actual method call
def first_name_vs_last_name_cleanup(array_of_input_strings)
	# create output array variable
	output_array = []
	# iterate over the array_of_input_strings
	for string in array_of_input_strings do
	# for each string in the input array
		# split string on '_'
		string_split = string.split('_')
		# assign left side of string split (index 0) as new variable
		last_name = string_split[0]
		# look at index 0 (first character of string), and apply upcase method. Add this to rest of original string
		last_name_upper = last_name[0].upcase + last_name[1..-1]
		# assign right side of string split (index 1) as new variable
		first_name = string_split[1]
		# look at index 0 (first character of string), and apply upcase method. Add this to rest of original string
		first_name_upper = first_name[0].upcase + first_name[1..-1]
		# interpolate "#{Firstname} #{Lastname}" as new string variable
		clean_full_name = "#{first_name_upper} #{last_name_upper}"
		# add interpolated string variable to output array
		output_array.push(clean_full_name)
	end
		# return output array
	return output_array
end

# Test Suite
def assertEquals(actual, expected, testName)
	if actual = expected then
		puts "passed '#{testName}': expected '#{expected}', and got '#{actual}'"
	else
		puts "failed '#{testName}': expected '#{expected}', but got '#{actual}'"
	end
end

input_strings = ['potter_harry', 'weasley_ronald', 'snape_severus']
output_strings = first_name_vs_last_name_cleanup(input_strings)
p assertEquals(input_strings, output_strings, 'It correctly formats the input strings into the proper Firstname Lastname format')

```





```
PseudoCode practice to detect if a given word/string is a palindrome:

function isPalindrome(string)
- assign input string to a variable
- iterate over the string
  - if each character of the string read forwards and backwards is the same
    - this is a palindrome, return true
  - otherwise,
   - this is not a palindrome, return false
```





```
PseudoCode practice exercise for a function to count the number of sheep in the barn:

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
# Actual method call
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
