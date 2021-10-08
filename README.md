# Postgres__jsonb_set
jsonb_set function basic use


Function used to define or edit an specifc property in a json object.
It works to json or jsonb, but using a normal json the function is json_set.

## Example 1:

Consider the following json:

```json
{
    "a": "apple",
    "b": "banana",
    "c": "orange"
}
```

If you want to add a property "d" in the json, via postgres, use jsonb_set like this:

```sql
-- v_json == example above
-- '{d}' == path (text[])
v_json = jsonb_set(v_json, '{d}', '"grape"');
```

_Exit:_

```json
{
    "a": "apple",
    "b": "banana",
    "c": "orange",
    "d": "grape"
}
```

Notice that the last value needs to be a json, because of that we use ".

## Example 2:

Consider the following json:

```json
{
    "a": "apple",
    "b": "banana",
    "c": "orange",
    "d": "grape"
}
```

If you want to edit the property "b" in the json, via postgres, use jsonb_set like this:

```sql
-- v_json == example above
-- '{d}' == path (text[])
v_json = jsonb_set(v_json, '{b}', '"lemon"');
```


_Exit:_

```json
{
    "a": "apple",
    "b": "lemon",
    "c": "orange",
    "d": "grape"
}
```
