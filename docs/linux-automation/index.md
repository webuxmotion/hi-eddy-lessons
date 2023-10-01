---
sidebar_position: 6
---

# Linux Automation

See **video** **[Linux Automation by DevOps01](https://youtu.be/FypODsQxJWI?si=r9ifRBLtRnfyrzpu)**.

## Arguments Example

Create file:

```bash title="argumets_example.sh"
echo "Number of argumets: $#"

echo "First argument: $1"
echo "Second argument: $2"

for arg in "$@"; do
    echo "Argument: $arg"
done
```

Run the script in console with 4 arguments:

```bash
sh argumets_example.sh one 2 three 3+1
```

See the result:

![](./img/argumets-example-running-command.png)

