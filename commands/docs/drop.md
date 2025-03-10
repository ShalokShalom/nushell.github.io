---
title: drop
categories: |
  filters
version: 0.84.0
filters: |
  Remove items/rows from the end of the input list/table. Counterpart of `skip`. Opposite of `last`.
usage: |
  Remove items/rows from the end of the input list/table. Counterpart of `skip`. Opposite of `last`.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> drop (rows)```

## Parameters

 -  `rows`: The number of items to remove


## Input/output types:

| input     | output    |
| --------- | --------- |
| list\<any\> | list\<any\> |
| table     | table     |
## Examples

Remove the last item of a list
```shell
> [0,1,2,3] | drop
╭───┬───╮
│ 0 │ 0 │
│ 1 │ 1 │
│ 2 │ 2 │
╰───┴───╯

```

Remove zero item of a list
```shell
> [0,1,2,3] | drop 0
╭───┬───╮
│ 0 │ 0 │
│ 1 │ 1 │
│ 2 │ 2 │
│ 3 │ 3 │
╰───┴───╯

```

Remove the last two items of a list
```shell
> [0,1,2,3] | drop 2
╭───┬───╮
│ 0 │ 0 │
│ 1 │ 1 │
╰───┴───╯

```

Remove the last row in a table
```shell
> [[a, b]; [1, 2] [3, 4]] | drop 1
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 1 │ 2 │
╰───┴───┴───╯

```


## Subcommands:

| name                                           | type    | usage                                                                                               |
| ---------------------------------------------- | ------- | --------------------------------------------------------------------------------------------------- |
| [`drop column`](/commands/docs/drop_column.md) | Builtin | Remove N columns at the right-hand end of the input table. To remove columns by name, use `reject`. |
| [`drop nth`](/commands/docs/drop_nth.md)       | Builtin | Drop the selected rows.                                                                             |