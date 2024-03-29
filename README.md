---


---

<hr>
<hr>
<h1 id="array-methods-in-javascript">Array Methods in JavaScript</h1>
<h3 id="list-of-array-methods">List of Array Methods</h3>
<p><a href="#map">Map</a><br>
</p><p><a href="#reduce">Reduce</a><br></p>
<p><a href="#filter">Filter</a><br></p>
<p><a href="#foreach">ForEach</a><br></p>
<p><a href="#sort">Sort</a><br></p>
<p><a href="#slice">Slice</a><br></p>
<p><a href="#pop">Pop</a><br></p>
<p><a href="#shift">Shift</a><br></p>
<p><a href="#unshift">Unshift</a><br></p>
<p><a href="#push">Push</a><br></p>
<p><a href="#includes">Includes</a><br></p>
<p><a href="#indexof">IndexOf</a><br></p>
<p><a href="#every">Every</a></p>
<p><a href="#charAt">charAt</a></p>
<h2 id="map">Map</h2>
<p>Array.prototype.map() returns a new array, with each element of that array modified based on a function that you pass into it.<br>
</p><p>Map is not destructive to the original array.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>A callback function which can accept the following as parameters:</p>
<ul>
</ul><li>the current element of the array (required)</li>
<li>the index of the current element</li>
<li>the array that map was called on</li>

<p>In addition to the callback function, it can also take in a value to use as <code>this</code> when calling the callback function</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.map(el =&gt; //return statement)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = ['Apple', 'Peach', 'Orange']

arr.map(el =&gt; el + '!')

  

// returns [ "Apple!", "Peach!", "Orange!" ]

</code></pre>
<pre><code>const arr = ['Apple', 'Peach', 'Orange']

arr.map((el, i) =&gt; i)

  

// returns [ 0, 1, 2 ]

</code></pre>
<pre><code>const arr = ['Apple', 'Peach', 'Orange']

arr.map((el, i) =&gt; {

return (i % 2 === 0) ? el.toUpperCase() : el

})

  

// returns [ "APPLE", "Peach", "ORANGE" ]

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="reduce">Reduce</h2>
<p>Array.prototype.reduce() uses something called a reducer function, which is called on the array that reduce is called on. What happens is the array is eventually reduced to one value, which becomes the return value of .reduce()!<br>
</p><p>Reduce is unique in that it also takes in a special (optional) initial value to kick off the .reduce() function.<br></p>
<p>Reduce will not affect the original array.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>The reducer function is passed to reduce, and can take four arguments:</p>
<ul>
</ul><li>the accumulator (required)</li>
<li>the current value (required)</li>
<li>the current index</li>
<li>the array that .reduce() was called on</li>

<p>Don’t forget - .reduce() can also take an optional initial value.</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.reduce(reducerFunction, initialValue)</code><br></p>
<p><em>or</em><br></p>
<p><code>someArray.reduce((acc, curr) =&gt; acc + curr, 0)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = [1,2,3,4,5]

arr.reduce((a, b) =&gt; a + b)

  

// returns 15

</code></pre>
<pre><code>const arr = ['1','2','3','4','5'] arr.reduce((a, b) =&gt; a + b)

  

// returns "12345"

</code></pre>
<pre><code>const arr = ['1','2','3','4','5'] arr.reduce((a, b) =&gt; a - b, 15)

  

// returns 0

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="filter">Filter</h2>
<p>Array.prototype.filter() will ‘filter’ an array based on a function that is passed into it. The function checks each element of the array, and the elements that pass the test will be returned in a new array!<br>
</p><p>Filter is not destructive to the original array.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>.filter() takes in a function which itself can take up to three parameters:</p>
<ul>
</ul><li>the current element (required)</li>
<li>index of the current element</li>
<li>the array that .fliter() was called on</li>

<p>In addition to the callback function, it can also take in a value to use as <code>this</code> when the function is called</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.filter(el =&gt; callbackFunction)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = [1,2,3,4,5,6,7,8]

arr.filter(el =&gt; el % 2 === 0)

  

//returns [ 2, 4, 6, 8 ]

</code></pre>
<pre><code>const arr = ['short', 'sesquipedalian', 'words', 'obsequious', 'only']

arr.filter(el =&gt; el.length &lt; 6) //returns [ 2, 4, 6, 8 ]

  

//returns [ "short", "words", "only" ]

</code></pre>
<pre><code>const arr = ['foo', 'bar', 'buzz', 'bat', 'hello']

arr.filter((el, i) =&gt; i % 2 === 0)

  

// returns even index items only: [ "foo", "buzz", "hello" ]

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="foreach">forEach</h2>
<p>Array.protoype.forEach() executes a function for each element in an array. It’s very much like a <code>for</code> loop. It does not affect the original array, and it returns <code>undefined</code>!</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>.forEach() takes a callback function much like the other Array methods we’ve studied so far. That function can take up to three parameters:</p>
<ul>
</ul><li>the current element (required)</li>
<li>the index of that element</li>
<li>the array that .forEach() is being called on</li>

<p>In addition to the callback function, it can also take in a value to use as <code>this</code> when the function is called</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.forEach(el =&gt; callbackFunction)</code></p>
<p>Some examples:</p>
<pre><code>const arr = ['Alan', 'Al', 'Alan', 'Allen', 'Alan'] const newArr = arr.forEach(el =&gt; console.log(el.concat('!')))

  

//will print the following to the console:

Alan!

Al!

Alan!

Allen!

Alan!

</code></pre>
<pre><code>const arr = ["chocolate chip cookie", "dried fruit", "candy", "sugar cookie", "bagel", "peanut butter cookie", "peanuts"] const cookies = [] const otherSnacks = [] arr.forEach(el =&gt; (el.includes('cookie')) ? cookies.push(el) : otherSnacks.push(el)) console.log(cookies, otherSnacks)

  

// prints cookies array and otherSnacks array:

[ "chocolate chip cookie", "sugar cookie", "peanut butter cookie" ]

[ "dried fruit", "candy", "bagel", "peanuts" ]

</code></pre>
<pre><code>const arr = [12, 13, 15, 62, 67, 48] arr.forEach(el =&gt; { console.log(`${el} is${(el % 4 === 0) ? "" : " not"} a multiple of 4.`) })

  

// prints the following:

12 is a multiple of 4.

13 is not a multiple of 4.

15 is not a multiple of 4.

62 is not a multiple of 4.

67 is not a multiple of 4.

48 is a multiple of 4.

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="sort">Sort</h2>
<p>Array.prototype.sort() sorts an array as strings by default, with smaller values first. It determines which one is smaller by checking the Unicode code point values.<br>
</p><p>.sort() sorts items “in place”, which means that the original array is changed.</p>
<p><em><strong>Time complexity:</strong></em> <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mtext>∗</mtext><mi>l</mi><mi>o</mi><mi>g</mi><mtext>⁡</mtext><mi>n</mi><mo stretchy="false">)</mo><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mo>∗</mo><mi>log</mi><mo>⁡</mo><mrow></mrow><mi>n</mi><mo stretchy="false">)</mo><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mtext>∗</mtext><mi>l</mi><mi>o</mi><mi>g</mi><mi>n</mi><mo stretchy="false">)</mo></mrow><annotation encoding="application/x-tex">O(n∗log⁡n)O(n *\log{}n)O(n∗logn)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 1em; vertical-align: -0.25em;"></span><span class="mord mathnormal" style="margin-right: 0.02778em;">O</span><span class="mopen">(</span><span class="mord mathnormal">n</span><span class="mord">∗</span><span class="mord mathnormal" style="margin-right: 0.01968em;">l</span><span class="mord mathnormal">o</span><span class="mord mathnormal" style="margin-right: 0.03588em;">g</span><span class="mord">⁡</span><span class="mord mathnormal">n</span><span class="mclose">)</span><span class="mord mathnormal" style="margin-right: 0.02778em;">O</span><span class="mopen">(</span><span class="mord mathnormal">n</span><span class="mspace" style="margin-right: 0.222222em;"></span><span class="mbin">∗</span><span class="mspace" style="margin-right: 0.222222em;"></span></span><span class="base"><span class="strut" style="height: 1em; vertical-align: -0.25em;"></span><span class="mop">lo<span style="margin-right: 0.01389em;">g</span></span><span class="mspace" style="margin-right: 0.166667em;"></span><span class="mord"></span><span class="mord mathnormal">n</span><span class="mclose">)</span><span class="mord mathnormal" style="margin-right: 0.02778em;">O</span><span class="mopen">(</span><span class="mord mathnormal">n</span><span class="mord">∗</span><span class="mord mathnormal" style="margin-right: 0.01968em;">l</span><span class="mord mathnormal">o</span><span class="mord mathnormal" style="margin-right: 0.03588em;">g</span><span class="mord mathnormal">n</span><span class="mclose">)</span></span></span></span></span><br>
</p><p>This can vary depending on what JS engine (or browser) is being used, and how many elements are in the array.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>The way sort works is it compares as strings by default, but you can pass a <em>compare function</em> to it. If a compare function is used, the items will be sorted by the return value of the compare function.<br></p>
<p>The compare function can take in two values:</p>
<ul>
</ul><li>the first element</li>
<li>the next element</li>

<p><em><strong>Basic usage:</strong></em></p>
<pre><code>someArray.sort((a, b) =&gt; compareFunc}

  

compareFunc(a, b){

if (a &lt; b) return -1

if (a &gt; b) return 1

return 0

}

</code></pre>
<p>or<br>
</p><p><code>someArray.sort((a, b) =&gt; a - b)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const names = ['Isabelle', 'Chevre', 'Aurora', 'Tom', 'Blathers', 'Brewster'] names.sort()

  

//returns:

[ "Aurora", "Blathers", "Brewster", "Chevre", "Isabelle", "Tom" ]

</code></pre>
<pre><code>const nums = [17,38,3,14,5,21,22,4]

  

console.log(nums.sort())

//prints:

[ 14, 17, 21, 22, 3, 38, 4, 5 ]

  

console.log(nums.sort((a,b) =&gt; a - b))

//prints:

[ 3, 4, 5, 14, 17, 21, 22, 38 ]

</code></pre>
<pre><code>const nums = [32,56,43,57,12,34]

nums.sort((a,b) =&gt; b - a)

  

//returns:

[ 57, 56, 43, 34, 32, 12 ]

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="slice">Slice</h2>
<p>Array.prototype.slice() extracts part of an array and then returns it.<br>
</p><p>It’s kind of like a slice of an array!</p>
<p>It does not affect the original array… however, if the the items in the arrays are objects, the new array will reference those objects. This means that if you try to alter an object in the new array, the original objects will be affected as well.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>.slice() can take two parameters:</p>
<ul>
</ul><li>start</li>
<li>end</li>

<p><code>start</code> indicates at which index the slice will begin, and <code>end</code> indicates the index where the slice ends. <code>start</code> will be included in the returned array, and the value at <code>end</code> will not.</p>
<p>You can use a negative number for <code>start</code>, which will cause .slice() to count from the end of the array.<br>
</p><p>If <code>start</code> is too large for the array, and empty array will be what comes back.</p>
<p>The value passed in as <code>end</code> works much like <code>start</code>, except that if it’s too large for the array, it will just count through the end of the array</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.slice(start, end)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = [ 1, 2, 3, 4, 5, 6, 9]

arr.slice()

  

//returns [ 1, 2, 3, 4, 5, 6, 9 ]

</code></pre>
<pre><code>const arr = ['a', 'b', 'c', 'd', 'e', 'f', 'g']

arr.slice(-3)

  

//returns: [ "e", "f", "g" ]

</code></pre>
<pre><code>const arr = ['a', 'b', 'c', 'd', 'e', 'f', 'g']

arr.slice(2, 100)

  

//returns: [ "c", "d", "e", "f", "g" ]

</code></pre>
<pre><code>const arr = [{name: "bob", rank: 10},{name: "helen", rank: 11},{name: "ariel", rank: 9}]

const slicedArr = arr.slice(0, 2)

slicedArr[0].rank = 22

console.log(arr[0], slicedArr[0])

  

//prints:

{ name: "bob", rank: 22 }

{ name: "bob", rank: 22 }

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="pop">Pop</h2>
<p>Array.prototype.pop() “pops” an element off of the end of an array, and returns it. It returns <code>undefined</code> if it’s called on an empty array.</p>
<p>It affects the original array!</p>
<p>You can use .pop() on array-like objects by using .call(arrayLikeObj).<br>
</p><p>See the last example.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>none!</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.pop()</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const trees = ["oak", "spruce", "birch", "cedar"]

trees.pop()

//returns: "cedar"

console.log(trees)

//prints: [ "oak", "spruce", "birch" ]

</code></pre>
<pre><code>const fruits = ["kiwi", "orange", "banana"]

//using slice to copy the fruits array, so we don't affect it!

const lastFruit = fruits.slice().pop()

console.log(fruits, fruitsCopy)

  

//prints:

[ "kiwi", "orange", "banana" ]

banana

</code></pre>
<pre><code>const things = { 0:'thing1', 1:'thing2', 2:'thing3', length: 3} //needs the length propoerty

const poppedThing = Array.prototype.pop.call(things)

console.log(things, poppedThing)

  

//prints:

{ 0: "thing1", 1: "thing2", length: 2 }

thing3

`

</code></pre>
<p>Here’s something really cool you can do with this method. You can use it in a loop like this:</p>
<pre><code>const arr = [1,2,3,4,5]

while (typeof (i = arr.pop()) !== 'undefined') {

console.log(i)

}

  

//prints:

5

4

3

2

1

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="shift">Shift</h2>
<p>Array.prototype.shift() behaves just like <a href="#pop">.pop()</a>, except it works on the beginning, or front of the array.<br>
</p><p>It affects the original array.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>none!</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.shift()</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = ['pink', 'purple', 'blue', 'grey'] arr.shift()

//returns: "pink"

console.log(arr)

//prints: [ "purple", "blue", "grey" ]

</code></pre>
<pre><code>

</code></pre>
<pre><code>const arr = ['bread', 'nacho cheese', 'lettuce', 'macaroni']

while ((i = arr.shift()) !== undefined) {

console.log(i)

}

  

//prints:

bread

nacho cheese

lettuce

macaroni

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="unshift">Unshift</h2>
<p>Array.prototype.unshift() is kind of like the opposite of .shift() - instead of removing an item from the beginning, or the front of an array, it adds an item (or more).<br>
</p><p>It modifies the original array, and its return value is the new length of the array.</p>
<p><em><strong>Parameters accepted:</strong></em></p>
<ul>
</ul><li>the element to add to the array</li>

<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.unshift(newElement)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const dinosaurs = ['stegosaurus', 'triceratops', 'diplodocus']

dinosaurs.unshift('ankylosaurus')

// returns: 4

  

console.log(dinosaurs)

//prints: [ "ankylosaurus", "stegosaurus", "triceratops", "diplodocus" ]

</code></pre>
<pre><code>const weekdays = ['thu', 'fri', 'sat']

weekdays.unshift('mon', 'tue', 'wed')

//returns: 6

  

console.log(weekdays)

//prints: [ "mon", "tue", "wed", "thu", "fri", "sat" ]

</code></pre>
<pre><code>const outOfOrder = ['thu', 'fri', 'sat']

outOfOrder.unshift('mon') //returns 4

outOfOrder.unshift('tue') //returns 5

outOfOrder.unshift('wed') //returns 6

  

console.log(outOfOrder)

//prints: [ "wed", "tue", "mon", "thu", "fri", "sat" ]

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="push">Push</h2>
<p>Array.prototype.push() is similar to <a href="#shift">.shift()</a>, except it adds one or more items to the end of an array.<br>
</p><p>It changes the original array, and the return value is the new length of the array.</p>
<p><em><strong>Parameters accepted:</strong></em></p>
<ul>
</ul><li>the element to add to the array</li>

<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.push(newElement)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const names = ['aria', 'pokey', 'mitsy'] names.push('oreo')

//returns: 4

  

console.log(names)

prints: [ "aria", "pokey", "mitsy", "oreo" ]

</code></pre>
<pre><code>const fish = ['bass', 'char', 'salmon']

fish.push('angelfish', 'parrotfish', 'sturgeon')

//returns: 6

  

console.log(fish)

//prints: [ "bass", "char", "salmon", "angelfish", "parrotfish", "sturgeon" ]

</code></pre>
<pre><code>const inventory = [{0: 'chamomile', qty: 6}, {1: 'hibiscus', qty: 2}, {2: 'peppermint', qty: 10}]

inventory.push({3: 'rooibos', qty: 10}, {4: 'linden', qty: 10})

  

//returns: 5

  

console.log(inventory)

//prints the following:

// an Array, [ {…}, {…}, {…}, {…}, {…} ] containing...

0: Object { 0: "chamomile", qty: 6 }

1: Object { 1: "hibiscus", qty: 2 }

2: Object { 2: "peppermint", qty: 10 }

3: Object { 3: "rooibos", qty: 10 }

4: Object { 4: "linden", qty: 10 }

length: 5

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="includes">Includes</h2>
<p>Array.prototype.includes() checks to see if a value passed into it exists in an array.<br>
</p><p>It returns <code>true</code> if it is found, and <code>false</code> if not.</p>
<p><em><strong>Parameters accepted:</strong></em></p>
<ul>
</ul><li>element to search for (required)</li>
<li>index to start the search from</li>

<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.Method(el, index)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = [1, 2, 3, 4, 5]

console.log(arr.includes(2)) //true

console.log(arr.includes(0)) //false

</code></pre>
<pre><code>const words = ['well', 'hello', 'there']

console.log(words.includes('hello')) //true

console.log(words.includes('the')) //false

</code></pre>
<pre><code>const arr = ['a', 'b', 'c', 'd', 'e']

arr.includes('b', 0) //true

arr.includes('b', 2) //false

arr.includes('b', -3) //false

arr.includes('b', -4) //true - starts search at 4 from end

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="indexof">IndexOf</h2>
<p>Array.prototype.indexOf() searches an Array for an element, and returns the index number of where that item is located.<br>
</p><p>If it’s not found, -1 will be returned.</p>
<p>The element that is being searched for has to match in <em>both</em> value and type for a match to happen. (i.e., ‘3’ and 3 will not match.)</p>
<!--***Time complexity:***&amp;#10;.includes() stops when the item is found, and will execute once for each element in the array.&amp;#10;This means its time complexity is in this range:&amp;#10;$O(1)$ to $O(n)$&amp;#10;This is just a guess so I have commented this out!-->
<p><em><strong>Parameters accepted:</strong></em></p>
<ul>
</ul><li>the element to find in the array (required)</li>
<li>index where the search will start</li>

<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.indexOf(el, index)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const animals = ['zebra', 'buffalo', 'nuthatch', 'puma']

animals.indexOf() // -1

animals.indexOf('nuthatch') // 2

animals.indexOf('Puma') // -1

</code></pre>
<pre><code>const nums = [1, 2, 3, 4, 6]

const n = await nums.indexOf(5)

if (n === -1) {

return 'not found'

} else {

return `found at index: ${n}`

}

// returns: "not found"

</code></pre>
<pre><code>const nums = [1, 2, 3, 4, 6]

  

function addNum(n, arr){

arr.push(n)

arr.sort()

}

  

function isInArray(n, arr){

if (arr.indexOf(n) == -1) {

console.log(n + " is not in the array")

addNum(n, arr)

} else {

console.log(n + " is already in the array")

}

}

  

isInArray(5, nums) //prints: "5 is not in the array"

console.log(nums) //prints: [ 1, 2, 3, 4, 5, 6 ]

  

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="every">Every</h2>
<p>Array.prototype.every() checks to see if every item passes a test that is given by a function.<br>
</p><p>If every element in the array has a ‘truthy’ value, .every() will return <code>true</code>. Otherwise it’ll return <code>false</code>.</p>
<p><em><strong>Parameters accepted:</strong></em><br>
</p><p>.every() takes in a callback function, which itself can take three arguments:</p>
<ul>
</ul><li>the current element (required)</li>
<li>the index of the current element</li>
<li>the original array that .every() was called on</li>

<p>In addition to the callback function, it can also take in a value to use as <code>this</code> when the function is called.</p>
<p><em><strong>Basic usage:</strong></em><br>
</p><p><code>someArray.every((el, index) =&gt; callbackFunc)</code></p>
<p><em><strong>Some examples:</strong></em></p>
<pre><code>const arr = [5, 4, 7, 29, 90]

arr.every(el =&gt; el &gt; 0) //returns: true

arr.every(el =&gt; el &gt; 5) //returns: false

</code></pre>
<pre><code>const duckDuckGoose = ['duck', 'duck', 'goose']

const duckDuckDuck = ['duck', 'duck', 'duck']

  

function isDuck(str){

return str === 'duck'

}

  

console.log(duckDuckGoose.every(isDuck)) //prints: false

console.log(duckDuckDuck.every(isDuck)) //prints: true

</code></pre>
<pre><code>const nums = [[1, 2, 16], [0, 101, 2], [99, 78, 34]]

nums.forEach(arr =&gt; {

console.log(`${JSON.stringify(arr)}... are all nums less than 100? `+ arr.every(el =&gt; el &lt; 100))

})

  

//prints:

[1,2,16]... are all nums less than 100? true

[0,101,2]... are all nums less than 100? false

[99,78,34]... are all nums less than 100? true

</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="charAt">charAt</h2>
<p>
charAt() is a method that returns the character from the specified index.
</p><p>Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character in a string, called  <strong>stringName,</strong>  is stringName.length – 1.</p>

<pre><code>string.charAt(index);
</code></pre>
<p><code>index</code><br>
An integer between  <code>0</code>  and  <code>str.length - 1</code>. If the  <code>index</code>  cannot be converted to the integer or no  <code>index</code>  is provided, the default is  <code>0</code>, so the first character of  <code>str</code>  is returned.</p>
<pre><code>var anyString = 'Brave new world';
console.log("The character at index 0   is '" + anyString.charAt()   + "'");
// No index was provided, used 0 as default

console.log("The character at index 0   is '" + anyString.charAt(0)   + "'");
console.log("The character at index 1   is '" + anyString.charAt(1)   + "'");
console.log("The character at index 2   is '" + anyString.charAt(2)   + "'");
console.log("The character at index 3   is '" + anyString.charAt(3)   + "'");
console.log("The character at index 4   is '" + anyString.charAt(4)   + "'");
console.log("The character at index 999 is '" + anyString.charAt(999) + "'");

</code></pre>
<p>These lines display the following:</p>
<pre><code>The character at index 0   is 'B'

The character at index 0   is 'B'
The character at index 1   is 'r'
The character at index 2   is 'a'
The character at index 3   is 'v'
The character at index 4   is 'e'
The character at index 999 is ''
</code></pre>
<p><a href="#list-of-array-methods">Back to the list</a></p>
<h2 id="section"></h2>
<p><strong>That’s it!</strong></p>
<p>Thanks for taking the time to check out my little reference manual on Array Methods.<br>
</p><p>Go forth and use the aforementioned methods to your heart’s content ✨</p>
<p>The ultimate reference for JavaScript features can be found at the <a href="https://developer.mozilla.org/en-US/">MDN WebDocs</a></p>

