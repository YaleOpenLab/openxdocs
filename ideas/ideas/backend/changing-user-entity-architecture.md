# Changing User-Entity Architecture

Currently in Opensolar, the user entity is the base class that other entities on the platform build on top. This however, has a disadvantage since it means different entities have the same publickey. To avoid this, a potential construction is to make create new users for each entity and somehow have something on the importing platform's end to identify that they all are indeed the same user.

This could also be done on openx's side by introducing a new base class called the "entity" which allows for supporting an array of public keys and encrypted seed passwords. The base user class' publickey  variable could also be converted into an array and new publickeys can be added whenever the user desires so.

