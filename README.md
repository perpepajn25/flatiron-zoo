This project is a practice of a has-many-through relationship in Ruby. Flatiron just opened a new zoo with a ton of animals that need to be kept. The zoo has Environments such as desert or aquarium. Each Zookeeper has many Environments, depicted by the ZookeeperEnvironment class. Each Zookeeper is also responible for many Animals. Each Animal belongs to a Species. 

Here are your domain models. Please diagram them out before you write any code to ensure your understanding of the environment is complete.

 1. Environment
    - has_many :Zookeepers, through: :ZookeeperEnvironments
    - has_many :Species, through: :Animals

 2. ZookeeperEnvironment
    - belongs_to :Zookeeper
    - belongs_to :Environment

 3. Zookeeper
    - has_many :Animals
    - has_many :Species, through: :Animals
    - has_many :Environments, through: :ZookeeperEnvironments

 4. Animals
    - belongs_to :Zookeeper
    - belongs_to :Species

 5. Species
    - has_many :Zookeepers, through: :Animals

## Deliverables
### You should be able to create a new environment by running:
  * jungle = Environment.new("jungle")
  * desert = Environment.new("desert")
  * swamp = Environment.new("swamp")
  * aquarium = Environment.new("aquarium")

### You should be able to create a new zookeeper by running:
  * matt = Zookeeper.new("Matt")
  * laura = Zookeeper.new("Laura")
  * alex = Zookeeper.new("Alex")

### You should be able to create a new zookeeper by running:
  * matts_jungle = ZookeeperEnvironment.new(jungle, matt)
  * lauras_desert = ZookeeperEnvironment.new(desert, laura)
  * alexs_swamp = ZookeeperEnvironment.new(swamp, alex)

###  You should be able to create a new animal by running:
  * monkey = Animal.new("monkey")
  * camel = Animal.new("camel")
  * alligator = Animal.new("alligator")
  * shark = Animal.new("shark")

### You should be able to create a new species:
  * mammals = Species.new("mammal")
  * reptile = Species.new("reptile")
  * fish = Species.new("fish")

### You should be able to add an environment to a zookeeper:
  * matt.add_environment(swamp)
  * laura.add_environment(aquarium)

### You should be able to add an animal to a species:
  * fish.add_animal(shark)
  * mammals.add_animal(monkey)

### You should be able to get all the animals in a species:
  * mammals.animals
  - // [monkey, camel]

### You should be able to get all the environments of a zookeeper:
  * matt.environments
  - // [jungle, swamp]
