# Setup
Please run `setup_clean.sh` in bash before working with this repository, this only needs to be run once after you clone the repo.

If you are not using a UNIX based shell (i.e. Windows) please run `git config --local include.path ../.gitconfig` in the root directory of the repo.

# Releases
Only tagged releases of this repository will contain generated code.

Run `git tag` to check for the latest tag, and `git checkout <tag>` to check it out.

## Note
This project is configured to use mutexes/ semaphores.
Your version of HALCoGen might have a bug with generating FreeRTOS code that enables mutexes.

This bug is documented [here](http://e2e.ti.com/support/microcontrollers/hercules/f/312/p/626490/2320355).

The workaround is to copy the `mpu_wrappers.c` file in `HALCoGen_fix` to `<Your HALCoGen Install>/drivers/FreeRTOS/portable/CCS/Coretex-R4/`.
You may want to rename the original file to something like `mpu_wrappers.c.old` just in case you want to restore it.
