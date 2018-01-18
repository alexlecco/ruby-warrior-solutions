# ruby-warrior-solutions beginner
-------------------------------------------------------------------------------------
https://www.bloc.io/ruby-warrior/#/warriors/328661/levels/6

```ruby
class Player
  def play_turn(warrior)
    if !warrior.feel(:backward).wall? && @direction != "right"
      if warrior.feel(:backward).captive?
        warrior.rescue!(:backward)
      else
        warrior.walk!(:backward)
      end
    else
      @direction = "right"
      
      if warrior.feel.enemy?
        warrior.attack!
      else
        if warrior.health != 20 && @health == warrior.health
          warrior.rest!
          @direction = "left"
        else
          warrior.walk!
        end
      end
      @health = warrior.health
      
    end
  end
end
```
-------------------------------------------------------------------------------------
https://www.bloc.io/ruby-warrior/#/warriors/328661/levels/7

```ruby
class Player
  def play_turn(warrior)
    if warrior.feel.wall?
      warrior.pivot!
    else
      if warrior.feel.enemy?
        warrior.attack!
      else
        if @health > warrior.health && @health < 5
          warrior.walk!(:backward)
        else
          if @health != 20
            warrior.rest!
          else
            warrior.walk!
          end
        end
      end
    end
    @health = warrior.health
  end
end
```
-------------------------------------------------------------------------------------
https://www.bloc.io/ruby-warrior/#/warriors/328661/levels/8

```ruby
class Player
  def play_turn(warrior)
    #warrior.feel(:backward).wall? ? warrior.walk! : warrior.shoot!
    if !warrior.look[2].empty? && !warrior.look[2].wall?
      warrior.shoot!
    else
      warrior.walk!
    end
  end
end
```


-------------------------------------------------------------------------------------
https://www.bloc.io/ruby-warrior/#/warriors/328661/levels/9

```ruby
class Player
  def play_turn(warrior)
    
    if warrior.look(:backward)[2].enemy?
      if warrior.look[2].captive?
        if warrior.look[1].enemy?
          warrior.shoot!
        else
          warrior.walk!
        end
      else
        warrior.pivot!
      end
    else
      if warrior.feel.captive?
        warrior.rescue!
      else
        warrior.walk!
      end
    end
    
  end
end
```
-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------

# ruby-warrior-solutions intemediate

https://www.bloc.io/ruby-warrior/#/warriors/252430/levels/1

```ruby
class Player
  def play_turn(warrior)
    warrior.walk!(warrior.direction_of_stairs)
  end
end
```
-------------------------------------------------------------------------------------

https://www.bloc.io/ruby-warrior/#/warriors/252430/levels/2

```ruby
class Player
  def play_turn(warrior)
    if warrior.feel(warrior.direction_of_stairs).enemy?
      warrior.attack!(warrior.direction_of_stairs)
    else
      warrior.walk!(warrior.direction_of_stairs)
    end
  end
end
```
-------------------------------------------------------------------------------------


https://www.bloc.io/ruby-warrior/#/warriors/252430/levels/3

```ruby
class Player
  def play_turn(warrior)
    if warrior.feel(:forward).enemy?
      warrior.bind!(:forward)
    else
      if warrior.feel(:backward).enemy?
        warrior.bind!(:backward)
      else
        if warrior.feel(warrior.direction_of_stairs).empty?
          warrior.walk!(warrior.direction_of_stairs)
        else
          warrior.attack!(warrior.direction_of_stairs)
        end
      end
    end
  end
end
```
-------------------------------------------------------------------------------------


https://www.bloc.io/ruby-warrior/#/warriors/252430/levels/4

```ruby
class Player
  def play_turn(warrior)
    
    if warrior.listen == []
      warrior.walk!(warrior.direction_of_stairs)
    else
      if warrior.listen[0].captive?
        if !warrior.feel(:backward).wall?
          warrior.walk!(:backward)
        else
          if warrior.feel(:right).empty?
            warrior.rescue!(:left)
          else
            warrior.rescue!(:right)
          end
        end
      else
        if warrior.feel(warrior.direction_of(warrior.listen[0])).empty?
          if warrior.health == 20
            warrior.walk!(warrior.direction_of(warrior.listen[0]))
          else
            warrior.rest!
          end
        else
          if warrior.health > 10
            warrior.attack!(warrior.direction_of(warrior.listen[0]))
          else
            warrior.walk!(:left)
          end
        end
      end
    end

  end
```
-------------------------------------------------------------------------------------


https://www.bloc.io/ruby-warrior/#/warriors/252430/levels/5

```ruby
```
-------------------------------------------------------------------------------------
