Dead simple config file parsing for ooc.

## How to use

```ooc
use zombieconfig
import zombieconfig

main: func {
    config := ZombieConfig new("yourapp.config")

    launchUI(config["width"] toInt(), config["height"] toInt())
}
```

### Adding defaults


```ooc
use zombieconfig
import zombieconfig

main: func {

    config := ZombieConfig new("empty.config", |base|
        base("width", "1024")
        base("height", "768")
    )

    launchUI(config["width"] toInt(), config["height"] toInt())
}
```

## Config file format

It's pretty simple, those are "key = value" pairs on separate lines.

Every value is a string, it's up to you to convert it to something else
whenever you want.

No nested configs, no references, no doctypes, no schemas, no validation.

Have fun!
