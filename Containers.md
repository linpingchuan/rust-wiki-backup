Containers in the standard libraries:

* Mutable:
    * `core::dlist` (doubly-linked list - uses @ but avoiding that would require `unsafe`)
    * `core::vec` (dynamic array)
    * `core::str` (string implemented on top of the same dynamic array as `core::vec`)
    * `core::hashmap` (hash table - set and map)
    * `std::treemap` (balanced binary search tree - set and map)
    * `std::smallintmap` (dense array-based map)
    * `std::deque` (ring buffer)
    * `std::priority_queue` (binary heap)
* Persistent:
    * `std::list` (singly-linked list)
    * `std::fun_treemap` (unbalanced binary search tree - not very useful)

Obsolete (to be removed):

* `std::dvec` (`~[]` in a mut field)
* `std::oldmap` (chaining-based hash table using lots of @ and mut fields)
* `std::oldsmallintmap` (like `std::smallintmap`, but with mut fields and a @ box)

Wanted:

* radix trie (IntMap, IntSet - perhaps more generic)
* b-tree (either in addition to `std::treemap` or replacing it)
* small vector (3-word struct storing small arrays on the stack)
* LRU cache (doubly-linked list and a hash table of key->index)
* persistent balanced binary search tree (map and set)
* persistent heap
* persistent hash-based map/set