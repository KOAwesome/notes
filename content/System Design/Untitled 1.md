      consistent hashing when we add new servers generally we try to partition from start but it fails cause users id is hashed in a way to reach server and we make wrong use of cache (image it as distributing a pie,)

      instead just take a little percentage from  

      every server
      
![[Pasted image 20251228110820.png]]



      One hit wonder →  

      Bloom filter we use a array to store bits ... We use hash function to search a string  

      Bloom filter guarantees when a string is not searched  

      Multi later bloom filters

       

      cap theorem → consistency or availability durring paritition(blockers)

