# ruby-warrior-solutions
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

```
