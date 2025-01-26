# Pizza Heroes

By Mouse Buttons

### Your Pizza Protocol Cient

Your **Pizza Protocol Client** must be:

- A binary executable available to install on any typical Windows, Mac OS, or Linux computer.

- Fully terminal-based. No graphic user interfaces.

It can be written in any language, it can be compiled or interpreted. What matters is that once a user installs it, they place a pizza order directly from the terminal, with just one command.

You can pick any command for your application. This is so multiple implementations of the pizza protocol (for different neighborhoods) can be installed on one system. For the purposes of this guide, the example command will be `pizz`.

#### The `pizz` command

Running the `pizz` command alone will print something like `git status`. It should inform the user:

- Is your client connected to your server?

- Is your pizza service open?
  
  - If so, what is the estimated wait time for cooking?

- Are any orders on their way to the user?
  
  - If so, what is the estimated delivery time?

- Tell the user to run `pizz menu` to see the menu, and run `pizz --help` for help

Running the `pizz default` subcommand will allow you to set default answers to order questions like your contact phone number, your address, and your usual order (see 'Subcommands').

`pizz` has these options:

- `-h` or `--help` to print help.

#### Subcommands

`pizz` has subcommands: `pizz order`, `pizz menu`, `pizz help`, and `pizz defaults`. They are technically subcommands and not options because there are no dashes prefixing them, and they will be parsed like separate commands.

##### Order

`pizz order` has these options:

- `-t` or `--toppings` to add toppings. Every kitchen is different; decide what toppings you will implement as parameters. Here are some examples:
  
  - `m` for mozzarella (default to this if no cheese is explictly given)
  
  - `rs` for red sauce (default to this if no sauce is explicitly given)
  
  - `ws` for white sauce
  
  - `ns` for no sauce
  
  - `r` for ricotta
  
  - `p` for pepperoni
  
  - `h` for ham
  
  - `hb` for hamburger
  
  If `order` is run without this option, default to the "usual-order" default. If no default is found, order a pizza with mozzarella cheese and red sauce.
  
  If a `/` is found, split the pizza in half (up to once)- toppings to the left of the `/` go on one side, toppings following the `/` go on the other side.

- `-s` or `--size` to set a size. Every kitchen is different; set your size options as parameters. Let users know what your available sizes are using `pizz menu`.
  
  If `order` is run without this option, default to your most reasonable size.

- `-a` or `--address` to set the delivery address. The address should be a string, and there are no strict formatting rules. There just needs to be enough information that a delivery driver can find the address.
  
  If `order` is run without this option, the command should fail. A delivery address is necessary for every order.

- `-p` or `--phone` to set the/ not required.

- `-n` or `--note` to send the order with a note. This covers special delivery instructions, allergy requirements or dietary restrictions, anything not covered in the options. The note should be a string.
  
  `order` can be run without this option.

After running `pizz order`, print a confirmation of the user's order- the toppings (unabbreviated), size, delivery address, phone number, and note if applicable. Also include an estimated cooking and delivery time based on their address. Let the user confirm their order with a y/N prompt.

Once the user confirms the order, print the estimated cooking and delivery time again.

##### Menu

`pizz menu` prints a menu for your pizza establishment. Type this up to your own taste. We recommend:

- A list of all your toppings and the abbreviations for them in `--toppings`.

- A list of your sizes and the abbreviations for them in `--size`.

- Your pricing scheme.

- Specialty pizzas or special offers.

- Your available options for dietary restrictions, and your accomodations for food allergies.

- Hours/open times.

##### Defaults

`pizz defaults` allows you to set default 




