```php
<?php
    class Vehicle {
        private $class;
        private $args;
        
        public static function build($vehicle) {
            $this->class = $vehicle;
            
            return $this;
        }
        
        public function args($args) {
            $this->args = $args;
            
            return $this;
        }
        
        public function run() {
            $class = new $this->class($this->args);
            $class->horn();
        }
    }
    
    class Car {
        private $args;
        public function __construct($args) {
            $this->args = $args;
        }
        
        public function horn() {
            echo "My name is :: " . $this->args['name'];
        }
    }
    
    Vehicle::build(Car::class)->args(["name" => "Bobby"])->run();
?>
```