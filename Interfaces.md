# Interfaces #

Even though JavaScript does not support interfaces, the js\_cols library defines some imaginary interfaces. This makes it easy to substitute one data structure with another without making further code changes.
For example, this might be if you initially used a Set and found out that you needed duplicates to be allowed.Then you would want to substitute with a Bag. Or if you started out using a SortedSet (based on Red-Black or (a, b) trees) and you found out that ordering did not matter after all. Then you would want to switch to a HashSet as this would improve performance on insertions and deletions from O(log<sub>n</sub>) to O(1).

## The interface hierarchy: ##
Available methods for each interface are listed in the diagram, and interfaces inherit methods from their "parents" and "grand parents".



![http://jscols.com/wp-content/uploads/InterFacesAll72.png](http://jscols.com/wp-content/uploads/InterFacesAll72.png)


<br><br>

<h2>Implementing classes:</h2>

<table><thead><th> <b>Interface</b> </th><th> <b>implementing classes</b></th></thead><tbody>
<tr><td> Collection       </td><td>ABTreeSet, ABTreeBag, RedBlackSet, RedBlackBag, HashSet, HashBag, LinkedList, Stack, Queue</td></tr>
<tr><td> Set              </td><td> ABTreeSet, RedBlackSet, HashSet </td></tr>
<tr><td>Bag               </td><td> ABTreeBag, RedBlackBag, HashBag </td></tr>
<tr><td>SortedSet         </td><td> ABTreeSet, RedBlackSet     </td></tr>
<tr><td> SortedBag        </td><td> ABTreeBag, RedBlackBag     </td></tr>
<tr><td> List             </td><td> LinkedList                 </td></tr>
<tr><td>Queue             </td><td> Queue                      </td></tr>
<tr><td> Stack            </td><td> Stack                      </td></tr>
<tr><td> Dictionary       </td><td> ABTreeMap, ABTreeMultiMap, RedBlackMap, RedBlackMultiMap, HashMap, HashMultiMap, LinkedHashMap</td></tr>
<tr><td>Map               </td><td> ABTreeMap, RedBlackMap, HashMap </td></tr>
<tr><td>MultiMap          </td><td> ABTreeMultiMap, RedBlackMultiMap, HashMultiMap</td></tr>
<tr><td>LinkedMap         </td><td> LinkedHashMap              </td></tr>
<tr><td>PriorityQueue     </td><td> IntervalHeap               </td></tr></tbody></table>

In general, use RedBlack Sets and Maps rather than ABTrees, as these are faster in normal web applications.<br>
ABTrees has been included as they can produce shallower trees, which are more cache effient when the data structure extends internal memory. They might be better than RedBlack trees in some server-side applications.