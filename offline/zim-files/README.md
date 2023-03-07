## Zim Files Readme

This directory must exist if you will use the Kiwix-serve container.

***IMPORTANT***: The `kiwix-serve` container will not run without any `.zim` files stored in the `./zim-files/` directory. At least one `.zim` file must exist in the `./zim-files/` directory.

Content can be downloaded from the [Kiwix library](https://library.kiwix.org/) (URL: https://library.kiwix.org/), as a `.zim` file then loaded into the Kiwix server.  If you are using `wget` or automation, use the [download.kiwix.org/zim](https://download.kiwix.org/zim/) site.

### Examples using `wget` to pull files

Here are some examples using the `wget` command to pull files from [https://download.kiwix.org/zim/](https://download.kiwix.org/zim/):
```
wget https://download.kiwix.org/zim/other/zimgit-water_en_2022-03.zim
wget https://download.kiwix.org/zim/zimit/rapsberry_pi_docs_2023-01.zim
wget https://download.kiwix.org/zim/wikipedia/wikipedia_en_for_schools_maxi_2023-02.zim
wget https://download.kiwix.org/zim/other/artofproblemsolving_en_all_maxi_2021-03.zim
wget https://download.kiwix.org/zim/stack_exchange/cooking.stackexchange.com_en_all_2022-11.zim
wget https://download.kiwix.org/zim/zimit/fas-military-medicine_en_2022-05.zim
wget https://download.kiwix.org/zim/other/zimgit-medicine_en_2022-03.zim
wget https://download.kiwix.org/zim/ted/ted_en_playlist-before-public-speaking_2021-01.zim
wget https://download.kiwix.org/zim/ted/ted_en_playlist-things-to-do-to-make-steam-lea_2022-08.zim
wget https://download.kiwix.org/zim/stack_exchange/gardening.stackexchange.com_en_all_2022-11.zim
```
