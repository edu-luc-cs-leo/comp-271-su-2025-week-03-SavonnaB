## Week 02 reflection
For week 02, we were given the heapifyUp method to complete in the repository.
My solution was very close except I did not treat the parent child numbers of the tree as positions but rather actual fixed numbers.
The solution that was given used indexes to represent parent/child positions.
I could understand why using the index function might be better in this circumstance because it auto-assigns the value to that position.
I think the issue here is natural logic in the way I code. I'm not looking at the code as having moving parts but each module as a stationary object.
// My Solution: 
//private void heapifyUp() {
        int child = this.usage - 1;
        int parent = parent(child);
        //SB: my mind goes immediately to defensive programming for situations like this. Honestly not 100% confident but hopefully this logic makes sense.
        while (child > 0 && this.underlying[child] < this.underlying[parent]) {
        swap(parent, child);
        child = parent;
        parent = parent(child);
        }
// Given Solution:
//private void heapifyUp() {
        // Start at the last inserted element
        int index = this.usage - 1;
        /*
         * The loop successively swaps any child and parent elements that violate the
         * min-heap property. Child is at position [index] and its parent at position
         * [parent(index)]. The loop stops when it encounters a child-parent pair that
         * does not violate the min-heap property or when it reaches the front of the
         * array.
         */
        while (parent(index) >= 0 &&
                this.underlying[index] < this.underlying[parent(index)]) {
            swap(parent(index), index);
            index = parent(index);
        }
    } // method heapifyUp

