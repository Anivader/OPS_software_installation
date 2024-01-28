## Step 1. 
Download github repository from https://github.com/feldman4/OpticalPooledScreens/tree/master

Download OpticalPooledScreens-master.zip and keep it in Ani/ folder

## Step 2. 
Unzip folder and go to directory
```
unzip OpticalPooledScreens-master.zip
cd OpticalPooledScreens-master
```
## Step 3.
Create Python 3 virtual environment
```
python3 -m venv venv
```
## Step 4.
add required packages to the virtual environment
```
sh install.sh

more install.sh
#!/usr/bin/env bash

# Look for installation instructions in README.md

. venv/bin/activate
pip install wheel
pip install -r requirements.txt
# link ops package instead of copying
# jupyter and snakemake will import code from .py files in the ops/ directory
pip install -e .

more requirements.txt
decorator==4.4.2
fire==0.4.0
joblib==0.13.2
matplotlib==3.1.3
natsort==7.0.1
networkx==2.4
notebook
numpy==1.18.1
pandas==1.0.3
Pillow==7.1.2
python-Levenshtein==0.12.2
PyYaml==5.4
scikit-image==0.18.1
scikit-learn==0.23.2
scipy==1.6.0
seaborn==0.10.1
six==1.14.0
snakemake==5.32.1
statsmodels==0.11.1
tqdm==4.46.0
openpyxl
xlrd
```

When I run the above code `sh install.sh` I got this message
```
Requirement already satisfied: wheel in ./venv/lib/python3.9/site-packages (0.42.0)
Collecting decorator==4.4.2 (from -r requirements.txt (line 1))
  Using cached decorator-4.4.2-py2.py3-none-any.whl (9.2 kB)
Collecting fire==0.4.0 (from -r requirements.txt (line 2))
  Using cached fire-0.4.0.tar.gz (87 kB)
  Preparing metadata (setup.py) ... done
Collecting joblib==0.13.2 (from -r requirements.txt (line 3))
  Using cached joblib-0.13.2-py2.py3-none-any.whl (278 kB)
Collecting matplotlib==3.1.3 (from -r requirements.txt (line 4))
  Using cached matplotlib-3.1.3.tar.gz (40.9 MB)
  Preparing metadata (setup.py) ... done
Collecting natsort==7.0.1 (from -r requirements.txt (line 5))
  Using cached natsort-7.0.1-py3-none-any.whl (33 kB)
Collecting networkx==2.4 (from -r requirements.txt (line 6))
  Using cached networkx-2.4-py3-none-any.whl (1.6 MB)
Collecting notebook (from -r requirements.txt (line 7))
  Using cached notebook-7.0.7-py3-none-any.whl.metadata (10 kB)
Collecting numpy==1.18.1 (from -r requirements.txt (line 8))
  Using cached numpy-1.18.1.zip (5.4 MB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... error
  error: subprocess-exited-with-error
  
  × Preparing metadata (pyproject.toml) did not run successfully.
  │ exit code: 1
  ╰─> [54 lines of output]
      Running from numpy source directory.
      <string>:461: UserWarning: Unrecognized setuptools command, proceeding with generating Cython sources and expanding templates
      /private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py:75: DeprecationWarning: distutils Version classes are deprecated. Use packaging.version instead.
        required_version = LooseVersion('0.29.14')
      /private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py:77: DeprecationWarning: distutils Version classes are deprecated. Use packaging.version instead.
        if LooseVersion(cython_version) < required_version:
      
      Error compiling Cython file:
      ------------------------------------------------------------
      ...
                  self.rng_state.ctr.v[i] = counter[i]
      
              self._reset_state_variables()
      
              self._bitgen.state = <void *>&self.rng_state
              self._bitgen.next_uint64 = &philox_uint64
                                         ^
      ------------------------------------------------------------
      
      _philox.pyx:195:35: Cannot assign type 'uint64_t (*)(void *) except? -1 nogil' to 'uint64_t (*)(void *) noexcept nogil'. Exception values are incompatible. Suggest adding 'noexcept' to type 'uint64_t (void *) except? -1 nogil'.
      Processing numpy/random/_bounded_integers.pxd.in
      Processing numpy/random/_philox.pyx
      Traceback (most recent call last):
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py", line 238, in <module>
          main()
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py", line 234, in main
          find_process_files(root_dir)
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py", line 225, in find_process_files
          process(root_dir, fromfile, tofile, function, hash_db)
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py", line 191, in process
          processor_function(fromfile, tofile)
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-install-xul0abu5/numpy_fa36bce59a49414d9f93ed289a3d172f/tools/cythonize.py", line 80, in process_pyx
          subprocess.check_call(
        File "/Library/Developer/CommandLineTools/Library/Frameworks/Python3.framework/Versions/3.9/lib/python3.9/subprocess.py", line 373, in check_call
          raise CalledProcessError(retcode, cmd)
      subprocess.CalledProcessError: Command '['/Users/gfeng/Documents/Ani/OpticalPooledScreens-master/venv/bin/python3', '-m', 'cython', '-3', '--fast-fail', '-o', '_philox.c', '_philox.pyx']' returned non-zero exit status 1.
      Cythonizing sources
      Traceback (most recent call last):
        File "/Users/gfeng/Documents/Ani/OpticalPooledScreens-master/venv/lib/python3.9/site-packages/pip/_vendor/pyproject_hooks/_in_process/_in_process.py", line 353, in <module>
          main()
        File "/Users/gfeng/Documents/Ani/OpticalPooledScreens-master/venv/lib/python3.9/site-packages/pip/_vendor/pyproject_hooks/_in_process/_in_process.py", line 335, in main
          json_out['return_val'] = hook(**hook_input['kwargs'])
        File "/Users/gfeng/Documents/Ani/OpticalPooledScreens-master/venv/lib/python3.9/site-packages/pip/_vendor/pyproject_hooks/_in_process/_in_process.py", line 149, in prepare_metadata_for_build_wheel
          return hook(metadata_directory, config_settings)
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-build-env-qt5uzqln/overlay/lib/python3.9/site-packages/setuptools/build_meta.py", line 366, in prepare_metadata_for_build_wheel
          self.run_setup()
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-build-env-qt5uzqln/overlay/lib/python3.9/site-packages/setuptools/build_meta.py", line 480, in run_setup
          super(_BuildMetaLegacyBackend, self).run_setup(setup_script=setup_script)
        File "/private/var/folders/jl/0yf38vf92t1_8f_bzyl_jvr40000gp/T/pip-build-env-qt5uzqln/overlay/lib/python3.9/site-packages/setuptools/build_meta.py", line 311, in run_setup
          exec(code, locals())
        File "<string>", line 488, in <module>
        File "<string>", line 469, in setup_package
        File "<string>", line 275, in generate_cython
      RuntimeError: Running cythonize failed!
      [end of output]
  
  note: This error originates from a subprocess, and is likely not a problem with pip.
error: metadata-generation-failed

× Encountered error while generating package metadata.
╰─> See above for output.

note: This is an issue with the package mentioned above, not pip.
hint: See above for details.
Obtaining file:///Users/gfeng/Documents/Ani/OpticalPooledScreens-master
  Preparing metadata (setup.py) ... done
Installing collected packages: ops-lasagna
  Attempting uninstall: ops-lasagna
    Found existing installation: ops-lasagna 0.1
    Uninstalling ops-lasagna-0.1:
      Successfully uninstalled ops-lasagna-0.1
  Running setup.py develop for ops-lasagna
Successfully installed ops-lasagna-0.1
```
##
```
ruby --version
ruby 2.6.10p210 (2022-04-12 revision 67958) [universal.arm64e-darwin23]
```
```
which ruby
/usr/bin/ruby
```

```
gem --version         
3.0.3.1
```
```
gem install aspera-cli
```
```
gem install aspera-cli
Fetching terminal-table-1.8.0.gem
Fetching webrick-1.8.1.gem
Fetching tty-cursor-0.7.1.gem
Fetching tty-spinner-0.9.3.gem
Fetching websocket-1.2.10.gem
Fetching xml-simple-1.1.9.gem
Fetching thread_safe-0.3.6.gem
Fetching unicode-display_width-1.8.0.gem
Fetching descendants_tracker-0.0.4.gem
Fetching coercible-1.0.0.gem
Fetching symmetric-encryption-4.6.0.gem
Fetching rubyzip-2.3.2.gem
Fetching ruby-progressbar-1.13.0.gem
Fetching net-ssh-7.2.1.gem
Fetching jwt-2.7.1.gem
Fetching execjs-2.9.1.gem
Fetching blankslate-3.1.3.gem
Fetching aspera-cli-4.15.0.gem
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory.
```

add these two lines in `~/.zshrc`
```
export GEM_HOME=$HOME/gems
export PATH=$HOME/gems/bin:$PATH
```
```
source ~/.zshrc
```
rerun the gem installation
```
gem install aspera-cli
```
successful
```
Fetching xml-simple-1.1.9.gem
Fetching thread_safe-0.3.6.gem
Fetching terminal-table-1.8.0.gem
Fetching websocket-1.2.10.gem
Fetching tty-spinner-0.9.3.gem
Fetching tty-cursor-0.7.1.gem
Fetching unicode-display_width-1.8.0.gem
Fetching webrick-1.8.1.gem
Fetching descendants_tracker-0.0.4.gem
Fetching coercible-1.0.0.gem
Fetching symmetric-encryption-4.6.0.gem
Fetching rubyzip-2.3.2.gem
Fetching ruby-progressbar-1.13.0.gem
Fetching net-ssh-7.2.1.gem
Fetching jwt-2.7.1.gem
Fetching execjs-2.9.1.gem
Fetching blankslate-3.1.3.gem
Fetching aspera-cli-4.15.0.gem
Successfully installed xml-simple-1.1.9
Successfully installed websocket-1.2.10
Successfully installed webrick-1.8.1
Successfully installed tty-cursor-0.7.1
Successfully installed tty-spinner-0.9.3
Successfully installed unicode-display_width-1.8.0
Successfully installed terminal-table-1.8.0
Successfully installed thread_safe-0.3.6
Successfully installed descendants_tracker-0.0.4
Successfully installed coercible-1.0.0
Successfully installed symmetric-encryption-4.6.0
RubyZip 3.0 is coming!
**********************

The public API of some Rubyzip classes has been modernized to use named
parameters for optional arguments. Please check your usage of the
following classes:
  * `Zip::File`
  * `Zip::Entry`
  * `Zip::InputStream`
  * `Zip::OutputStream`

Please ensure that your Gemfiles and .gemspecs are suitably restrictive
to avoid an unexpected breakage when 3.0 is released (e.g. ~> 2.3.0).
See https://github.com/rubyzip/rubyzip for details. The Changelog also
lists other enhancements and bugfixes that have been implemented since
version 2.3.0.
Successfully installed rubyzip-2.3.2
Successfully installed ruby-progressbar-1.13.0
Successfully installed net-ssh-7.2.1
Successfully installed jwt-2.7.1
Successfully installed execjs-2.9.1
Successfully installed blankslate-3.1.3
Successfully installed aspera-cli-4.15.0
Parsing documentation for xml-simple-1.1.9
Installing ri documentation for xml-simple-1.1.9
Parsing documentation for websocket-1.2.10
Installing ri documentation for websocket-1.2.10
Parsing documentation for webrick-1.8.1
Installing ri documentation for webrick-1.8.1
Parsing documentation for tty-cursor-0.7.1
Installing ri documentation for tty-cursor-0.7.1
Parsing documentation for tty-spinner-0.9.3
Installing ri documentation for tty-spinner-0.9.3
Parsing documentation for unicode-display_width-1.8.0
Installing ri documentation for unicode-display_width-1.8.0
Parsing documentation for terminal-table-1.8.0
Installing ri documentation for terminal-table-1.8.0
Parsing documentation for thread_safe-0.3.6
Installing ri documentation for thread_safe-0.3.6
Parsing documentation for descendants_tracker-0.0.4
Installing ri documentation for descendants_tracker-0.0.4
Parsing documentation for coercible-1.0.0
Installing ri documentation for coercible-1.0.0
Parsing documentation for symmetric-encryption-4.6.0
Installing ri documentation for symmetric-encryption-4.6.0
Parsing documentation for rubyzip-2.3.2
Installing ri documentation for rubyzip-2.3.2
Parsing documentation for ruby-progressbar-1.13.0
Installing ri documentation for ruby-progressbar-1.13.0
Parsing documentation for net-ssh-7.2.1
Installing ri documentation for net-ssh-7.2.1
Parsing documentation for jwt-2.7.1
Installing ri documentation for jwt-2.7.1
Parsing documentation for execjs-2.9.1
Installing ri documentation for execjs-2.9.1
Parsing documentation for blankslate-3.1.3
Installing ri documentation for blankslate-3.1.3
Parsing documentation for aspera-cli-4.15.0
Installing ri documentation for aspera-cli-4.15.0
Done installing documentation for xml-simple, websocket, webrick, tty-cursor, tty-spinner, unicode-display_width, terminal-table, thread_safe, descendants_tracker, coercible, symmetric-encryption, rubyzip, ruby-progressbar, net-ssh, jwt, execjs, blankslate, aspera-cli after 5 seconds
18 gems installed
```
```
ascli --version          
4.15.0
```
```
which ascli
/Users/gfeng/gems/bin/ascli
```

```
ascli conf ascp install
W, [2024-01-27T16:11:18.440224 #37921]  WARN -- : No config file found. New configuration file: /Users/gfeng/.aspera/ascli/config.yaml
W, [2024-01-27T16:11:19.000264 #37921]  WARN -- : Note that a future version will require Ruby version 3.0 at minimum, you are using 2.6.10
 Time: 00:00:21 ========================================================================================================================= 100% 40 Mbps Time: 00:00:21
Installed version 1.1.1.52
Saving config file.
```

```
find / -type f -name ascp 2>/dev/null
/System/Volumes/Data/Users/gfeng/.aspera/sdk/ascp
/Users/gfeng/.aspera/sdk/ascp
```
add these two lines in `~/.zshrc`
```
export PATH=$PATH:/Users/gfeng/.aspera/sdk
```
```
source ~/.zshrc
```
```
ascp --version 
IBM Aspera SDK version 1.1.1.52
ascp version 4.4.2.572 7fd3699
Operating System: MacOSX
FIPS 140-2-validated crypto ready to configure
AES-NI Supported
Connect Server License max rate=(unlimited), account no.=1, license no.=53
Enabled settings: connect, cargo, drive and sync2
```

```
which ascp
/Users/gfeng/.aspera/sdk/ascp
```


## Next
```
source venv/bin/activate
```

## Next
```
pip install 'cellpose[gui]'
```
Note, this is different than provided in github readme. You need to add '' around cellpose[gui]
