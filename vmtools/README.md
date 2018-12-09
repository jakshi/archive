# Repository description
Simple tool to create test VMs

# Introduction

vmtools is a tool for recreate test VMs.

It basically:

1. Create VM with vagrant.
2. Tring to start chef-client on this VM and add node to opscode hosted chef server.

vmtools have following parts:

* vmtools.rb util - executable file with code
* vmtconfig.rb - vmtools config with VM parameters. Default vmtconfig.rb populated to /usr/lib/ruby/gems/1.9.1/gems/vmtools-0.2.0/config/vmtconfig.rb dir. parameters from vmtconfig substitutes in Vagrantfile.erb template and generate resulting Vagrantfile.
* Vagrantfile.erb - erb template for Vagrantfile. Default Vagrantfile.erb is in the /usr/lib/ruby/gems/1.9.1/gems/vmtools-0.2.0/templates/Vagrantfile.erb dir

# Installation

     gem install vmtools

# Usage
## Getting started

Steps to start using vmtools:

1. Install vmtools

        gem install vmtools
 
2. Run vmtools and create VM:

        vmtools.rb -c

## Configuration

  * There is vmtconfig.rb and Vagrantfile.erb files with vmtools configuration settings.
  * if there's no vmtconfig.rb and Vagrantfile.erb files in current dir, vmtools use vmtconfig.rb and Vagrantfile.erb files from these directories: 

        /usr/lib/ruby/gems/1.9.1/gems/vmtools-0.2.0/config/vmtconfig.rb
        /usr/lib/ruby/gems/1.9.1/gems/vmtools-0.2.0/templates/Vagrantfile.erb.

  * You can copy these files to current dir and change it according you needs.
  * vmtools generate Vagrantfile from Vagrantfile.erb template. Usually it will be enough just to fill vmtconfig.rb, but if you want in resulting Vagrantfile something that vmtconfig.rb file didn't cover - please mend Vagrantfile.erb template.
  * note that if you will not change configs - chef part of vmtools will not work.

## vmtools commands
vmtools have following commands:

* -c, --create                     Create new VM according to config file
* -d, --delete                     Delete VM according to config file
* -r, --recreate                   Delete current VM and then create new VM according to config file
* -v, --version                    Print version info
* -h, --help                       Show short help

# Versions
stable versions:

* 0.x - stable versions
* 0.x.x - bug fixes for stable version

development brench haven't versions.

# Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

# License and Author

Author:: Lysenko Konstantin (<konstantin@atalanta-systems.com>)

Copyright:: 2012, Atalanta Systems LTD

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
