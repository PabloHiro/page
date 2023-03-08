---
title: "Dictionaries and lists in Ansible"
classes: wide
---

Today I had the chance to explain to a colleague how dictionaries and lists are defined in **Ansible**. The information in this post can be useful to understand how Python, JSON and YAML handle data structures, as some of the patterns shown here are used by these tools. I will use YAML for the examples as it is the most commonly used format for **Configuration as Code**

Let's tackle initializating first. Dictionaries use `{}`, lists use `[]`.

```
empty_dict: {}

empty_list: []
```

Dictionaries can be populated in two ways, both equivalent.

```
my_dict: {key: 'value', kee: 'bar'}

my_dict:
  key: 'value'
  kee: 'bar'
```

Same with lists:

```
my_list: ['first', 'second', 'third']

my_list:
  - first
  - second
  - third
```

Things get complicated when both data structures are nested, so I am leaving some examples below, which hopefully will help you identify easily these structures.

```
list_of_dictionaries: [first_key: 'first_value', second_key: 'second_value']

list_of_dictionaries:
  - { first_key: 'first_value' }
  - { second_key: 'second_value' }


dictionary_of_lists: {first_list: ['one', 'two', 'three'], second_list: ['four', 'five', 'six']}

dictionary_of_lists:
  first_list:
    - one
    - two
    - three
  second_list:
    - four
    - five
    - six
```

And the data above can be queried as follows:

```
# To retrieve 'second_value'
list_of_dictionaries[1]['second_key']

# To retrieve 'three'
dictionary_of_lists['first_list'][2]
```

