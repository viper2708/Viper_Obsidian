## What is Git and How Does it Works

* What is Git?
    * Version Control System
        * Software designed to record changes made to files over time
        * Ability to revert back to a previous file version or project version
        * Compare changes made to files from one version to another
        * Version control any plain text file, not just source code
    * Git uses snapshots, not differences
    * Everything in Git is check-summed
        * SHA1 hashing algorithm
    * The three stages of a file
        * Committed - Unmodified changes from the last commit snapshot
        * Modified - Changes made to files since last commit
        * Staged - Changes marked to be added into the next commit snapshot