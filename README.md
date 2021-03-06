![Travis](https://travis-ci.org/nawns/DinoDex.svg)
[![Coverage Status](https://coveralls.io/repos/nawns/DinoDex/badge.svg?branch=master&service=github)](https://coveralls.io/github/nawns/DinoDex?branch=master)

Usage:

Make a DinoDex object and call query with a hash of your parameters. Hash key naming goes by the original csv names, and should be capitalized. You can chain any number of arbitrary queries, and use the clear method to clear the searches and get the original csvs back. You can also use a Range value for Weight_in_lbs, and I've predefined BIG_SIZE and SMALL_SIZE constants. I've also set up some tests as well.

Example queries:

dinodex = DinoDex.new

* dinodex.query(Weight_in_lbs: DinoDex::BIG_SIZE).to_names
* dinodex.query(Weight_in_lbs: DinoDex::SMALL_SIZE).to_json
* dinodex.query(Diet: "Carnivore").query(Walking: "Quadruped").to_names
* dinodex.query(Walking: "Biped", Period: "Cretaceous").to_names
* dinodex.query(Weight_in_lbs: (525..2422)).to_json
* dinodex.query(Period: "Cretaceous").query(Diet: "Insectivore").facts
