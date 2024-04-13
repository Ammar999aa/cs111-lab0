# A Kernel Seedling

This kernel module create a new proc file /proc/count that outputs the number of currently running processes.

## Building

To build, navigate to the directory and run the following command

```shell
make
```

## Running

To run, first load the module into the kernel

```shell
sudo insmod proc_count.ko
```

Then run the program by using

```shell
cat /proc/count
```

The result I received on my run was 150.

## Cleaning Up

We remove the kernel module by running

```shell
sudo rmmod proc_count
```

and then clear the build environment

```shell
make clean
```

## Testing

```python
python -m unittest
```

After running the test I got:

ran 3 tests in 19.946s

OK

That means it passed all three tests.

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```

The output of the command states that the version is Linux 5.14.8-arch1-1
