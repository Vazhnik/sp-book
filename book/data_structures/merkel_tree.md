## Links
https://brilliant.org/wiki/merkle-tree/


## Brief
A Merkle tree is a hash-based data structure that is a generalization of the hash list.
It is a tree structure in which each leaf node is a hash of a block of data, and each non-leaf node is a hash of its children.
Typically, Merkle trees have a branching factor of 2, meaning that each node has up to 2 children.

## Details

Бенефиты от использования: уменьшение данных пересылаемых по сети.
Например нужно сравнить, что данные среплицировались на несколько нод, чтобы проверить, что репликация прошла без ошибок стоит использовать Merkel tree.
Нода посчитает root hash данных и перешлёт его на мастер ноду. Если хеш правильный, то и данные правильные, если нет - нужно искать блок данных с проблемой.

Пример:
1. Computer A sends a hash of the file to computer B.
1. Computer B checks that hash against the root of the Merkle tree.
1. If there is no difference, we're done! Otherwise, go to step 4.
1. If there is a difference in a single hash, computer B will request the roots of the two subtrees of that hash.
1. Computer A creates the necessary hashes and sends them back to computer B.
1. Repeat steps 4 and 5 until you've found the data blocks(s) that are inconsistent. It's possible to find more than one data block that is wrong because there might be more than one error in the data.

