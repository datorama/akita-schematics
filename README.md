# Akita Schematics

**Deprecated** - Use `ng add @datorama/akita`

Scaffolding library for Angular applications using Akita.

akita-schematics provides CLI commands for generating files when building new features with Akita. Built on top of [`Schematics`](https://blog.angular.io/schematics-an-introduction-dc1dfbc2a2b2), this tool integrates with the [`Angular CLI`](https://cli.angular.io/).

### Installation

Install akita-schematics from npm:

`npm install akita-schematics --save-dev`

##### OR

`yarn add akita-schematics --dev`

## Default Schematics Collection

To use `akita-schematics` as the default collection in your Angular CLI project,
add it to your `angular.json`:

```sh
ng config cli.defaultCollection akita-schematics
```

The [collection schema](https://github.com/datorama/akita-schematics/blob/master/src/collection.json) also has aliases to the most common schematics used to generate files.

The `akita-schematics` extend the default `@schematics/angular` collection. If you want to set defaults for schematics such as generating components with scss file, you must change the schematics package name from `@schematics/angular` to `akita-schematics` in `angular.json`:

```json
"schematics": {
  "akita-schematics:component": {
    "styleext": "scss"
  }
}
```

## Create a New Feature

```sh
ng g akita-schematics:feature todos/todos
```

The defauls feature will output an entity feature, but you can also generate the normal:

```sh
ng g akita-schematics:feature todos/todos --plain
```

> Note that the `akita-schematics:` prefix is only needed when the default collection isn't set to `akita-schematics`

## Generate a Store

```sh
ng g akita-schematics:as todos
ng g akita-schematics:aes todos // entity store
```

## Generate a Query

```sh
ng g akita-schematics:query todos
ng g akita-schematics:entity-query todos

Alias:
ng g akita-schematics:aq todos
ng g akita-schematics:aeq todos // entity query
```

## Generate a Model

```sh
ng g akita-schematics:model todo

Alias:
ng g akita-schematics:am todo
```

## Generate a Service

```sh
ng g akita-schematics:service todos

Alias:
ng g akita-schematics:asr todos
```

## Generate Tests

Add the `--spec` option. For example:

`ng g af products/products --spec`

## Generate Module

Add the `--withModule` to generate module and akita component. (only for entity store)
