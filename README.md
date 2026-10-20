![img/cover.png](img/cover.png)

# Embedded Compile and Upload <!-- omit from toc -->

A collection of tools and descriptions for compiling and uploading firmware for the more used microcontroller families

Every variant has tools and documentation to do these actions:

1. **Compile**: Compile source code into one or more binary file(s)
2. **Upload**: Upload the compiled binary file(s) onto the microcontroller
3. **Debug**: Debug the uploaded firmware

## Common firmware

For simplicity, the same program is used for each variant, which is the classic **blink** program. If the variant has an UART available, the current LED state will be printed to it.

```mermaid
flowchart TD
    a1[configure MCU]
    a1 --> a2(( ))
    a2 --> a3[turn LED on]
    a3 --> a4[wait 1s]
    a4 --> a5[turn LED off]
    a5 --> a6[wait 1s]
    a6 --repeat--> a2
    subgraph b[UART]
        b4[print '1']
        b5[print '0']
    end
    a3 --> b4
    b4 --> a4
    a5 --> b5
    b5 --> a6
```
