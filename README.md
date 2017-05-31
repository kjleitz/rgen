# rgen

Basic bash script to generate React component file stubs. Not the greatest. Pretty hacky. But it'll do. _It'll do._

## Installation

Run the following at your own risk. I don't think there really _is_ much of a risk, unless you've already installed some utility called `rgen` and you end up copying over it or creating a duplicate reference. If you're worried that you've already installed something called `rgen`, run `which rgen` before these instructions. If there's no output, you're good to go. If `rgen` already exists, just rename the script after you've cloned it and run the remaining three commands with the new name wherever it says "`rgen`". I've already said too much. Now you've got me rambling.

```
$ git clone https://github.com/kjleitz/rgen
$ cd rgen
$ chmod 755 rgen
$ cp rgen /usr/local/bin/rgen
```

## Usage

Right now, all you can do with `rgen` is generate component stubs like this:

```
$ rgen component Button

or

$ rgen component Button.js

or

$ rgen c Button
```

- As per convention, you should capitalize the component name. You don't have to, but keep in mind that `rgen` will not capitalize it for you.
- It doesn't matter if you add the .js extension or not.
- If you have a `components` subdirectory in the directory you're in, it will store the new file (`Button.js`) there. If you don't, it will be created wherever you run the command.
- You can use `c` as shorthand for `component`

If you specify a path, like this:

```
$ rgen component some/path/to/Button

or

$ rgen component some/path/to/Button.js
```

...then it will create the component there. The directory has to exist, though. If you have a `components` subdirectory but you do _not_ want the component file to be created there, do this:

```
$ rgen component ./Button

or

$ rgen component ./Button.js
```

...which will create the component file in the directory you're in, and will disregard the `components` directory.

## Output

Once you've created your component stub, find it in the `components` subdirectory, the root of your app, or wherever the hell you decided to put it. If you used one of the previous example commands, your file would be named `Button.js`, and inside it would look like this:

```js
import React from 'react';

export default class Button extends React.Component {
  render() {
    return (
      <div></div>
    );
  }
}
```

I hope that's how you like it.

## Future

I may add other generators later, hence the pre-emptive `component` argument. I also might move the component template out into its own file, so that `rgen` copies from that file as opposed to just planting a hard-coded string into the created file. That way, you could modify that template to suit your own needs. Unfortunately for poor little `rgen`, this works perfectly well for my needs, currently. If other people end up using this tool, I'll definitely put some real effort into it.

## Contributing

Bug reports and pull requests for this project are welcome at its [GitHub page](https://github.com/kjleitz/cadu). I know this is bash, but if you choose to contribute, please adhere to the [Ruby Community Conduct Guideline](https://www.ruby-lang.org/en/conduct/) so I don't have to go around breaking necks, running out of bubblegum, etc. If you'd like to make a suggestion for new features, make them in the "Issues" section and I'll try to get around to implementing them.

## License

This project is open source, under the terms of the [MIT license](https://opensource.org/licenses/MIT).
