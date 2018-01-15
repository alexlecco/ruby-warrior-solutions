# ruby-warrior-solutions
-------------------------------------------------------------------------------------
https://www.bloc.io/ruby-warrior/#/warriors/328661/levels/6

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
-------------------------------------------------------------------------------------
