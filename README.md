# alcc-2015-benchmarks
Benchmarks used for my 2015 ALCC proposal

## Usage
You can create and build a benchmark in one of two ways: 
 - Manualy, with pattern-matching, genbox, genmap, and makenek
 - Automagically, with genrun and makenek
 
### Manual instructions
 1. Find an existing benchmark that contains a `.usr`, `.rea`, `.box`, and `SIZE` file
 2. Change `nelx`, `nely`, `nelz` in the `.box` file
 3. Change `lelg` and `lp` in the `SIZE` file
 4. `my_shape` in the `.usr` file to match `{nelx, nely, nelz}`
 5. Change `p65` in the `.rea` file to be some factor of `lp`
 6. Run `genbox` to update mesh information in the `.rea` input file
 7. Run `genmap` to create a `.map` input file
 8. Run `makenek` to build the executable

### Automagic instructions
 1. Copy any of the `.json` files into a new directory
 2. Edit `procs`, `shape_mesh`, and `io_files` to get the right scale
 3. clone or download maxhutch/nek-tools
 4. Run `genrun.py -d *.json -u ../iturb_f77.tusr --map --legacy my_benchmark`
