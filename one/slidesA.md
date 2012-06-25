!SLIDE title-slide

# Having Fun
# in Ruby

!SLIDE bullets transition=scrollLeft

# Overview

* Chingu gem
* Resources

!SLIDE bullets

# Anatomy of a simple game

    @@@ ruby
    Chingu::Window

    Chingu::GameObject


!SLIDE

## Window

    @@@ ruby
    class Game < Chingu::Window
      def initialize
        super
        self.input = { :escape => :exit }

      end

      def update
        super
        self.caption = "FPS: #{self.fps}"
      end
    end

!SLIDE

## Game Objects

    @@@ ruby
    class Player < Chingu::GameObject
      def initialize
        super
        self.x, self.y = 200, 200
        self.image = Image["ship.png"]
        self.input = {
            :holding_left  => :move_left,
            :holding_right => :move_right }
      end

      def move_left;  @x -= 3; end
      def move_right; @x += 3; end
    end

    Player.create
	
!SLIDE bullets

## Input

    @@@ ruby
    self.input => {:holding_x => :command}

    :holding_x  = 'every frame'
    :x          = 'key down'
    :released_x = 'key up'


!SLIDE bullets

## Sound

    @@@ ruby
    class SpaceShip < Chingu::GameObject
      def initialize
        self.input = {:space => :pewpew}
      end

      def pewpew
        Sound["blaster.wav"].play
      end
    end

!SLIDE smbullets

## Traits (aka modules)

* Timers
* Collision
* BoundingArea (Square/Circle)
* Velocity
* Animation

!SLIDE

## Collision Trait

    @@@ ruby
    class Asteroid < Chingu::GameObject
      traits :bounding_circle,
             :collision_detection
    end

    # in your gamestate or window
    def update
      Player.each_collision(Asteroid) do |p,a|
        p.destroy
      end
    end

!SLIDE smbullets

## States

### A stack to manage menus, levels, pausing.

    @@@ ruby
    class Level < Chingu::GameState
      # initialize/update here
    end

    class Game < Chingu::Window
      def initialize
        push_game_state(Level)

        # A built in editor!
        push_game_state(Chingu::GameStates::Edit)
      end
    end


!SLIDE

## Saving/Loading

    @@@ ruby
    class Level < Chingu::GameState
      def initialize
        load_game_objects

        self.input = {:s => :save_game_objects}
      end
    end


!SLIDE

## Put it all together!


!SLIDE smbullets

## Resources

* Chingu (And some finished game links)
  * github.com/ippa/chingu
  * github.com/jlnr/gosu/blob/master/examples/ChipmunkIntegration.rb

* Sound
  * www.bfxr.net (Random SFX Generator)
  * www.freesound.org (Categorized sound clips)

* Music
  * www.soundcloud.com (Creative Commons)
  * www.freemusicarchive.org (Creative Commons)

* Graphics
  * www.pixeljoint.com (8-bit artist community)
  * www.deviantart.com (Search 'sprite', Commissions)

!SLIDE bullets center transition=scrollUp
# EOF #
Thanks!

* github.com/zeroeth
* @kevinalford
* pixelflow.org

