+++
date = "2015-12-21T15:18:08+08:00"
draft = true
title = "Beam Search Algorithm"
categories = [
    "algorithm"
]
+++
Beam Search Algorithm uses a heuristic function and a given beam width in an attempt to simulate the Breadth-First Search in a memory-efficient way.
<!--more-->
Pseudocode for the Beam Search Algorithm:

<pre>
<code class="js" style="font-size:10px;">
/* initialization */
g = 0;
hash_table = { start };
BEAM = { start };

/* main loop */
while(BEAM ≠ ∅){                             // loop until the BEAM contains no nodes
  SET = ∅;                                   // the empty set

  /* generate the SET nodes */
  for(each state in BEAM){
    for(each successor of state){
      if(successor == goal) return g + 1;
      SET = SET ∪ { successor };             // add successor to SET
    }
  }

  BEAM = ∅;                                  // the empty set
  g = g + 1;

  /* fill the BEAM for the next loop */
  while((SET ≠ ∅) AND (B > |BEAM|)){         // set not empty and nodes in BEAM less than B
    state = successor in SET with smallest h value;
    SET = SET \ { state };                   // remove state from SET
    if(state ∉ hash_table){                  // state is not in the hash_table
      if(hash_table is full) return ∞;
      hash_table = hash_table ∪ { state };   // add state to hash_table
      BEAM = BEAM ∪ { state };               // add state to BEAM
    }
  }
}

// goal was not found, and BEAM is empty - Beam Search failed to find the goal
return ∞;
</code>
</pre>
