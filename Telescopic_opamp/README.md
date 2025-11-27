Telescopic Opamp using xschem and Ngpice

And here is the gain-frequency plot


<img width="615" height="508" alt="image" src="https://github.com/user-attachments/assets/7a680de9-4f47-45d2-87d9-bcd2a56b61bb" />


## 🔍 How to Find the SKY130 Model File??

If you need to locate the SKY130 model file (`sky130.lib.spice`) on your Linux system, run this command:

```bash
sudo find / -type f -name "sky130.lib.spice" 2>/dev/null
```

This will search your entire filesystem and print the full path of the model file.
And select the appropriate path and copy to file in the schmatic.

##  How to Plot the frequency repsonse??
Enter this command in the after simulatig in the ngspcie command terminal
```bash
plot db(v(vout)/v(vip))
```
Change the names according to the pins you used in the schematic.
