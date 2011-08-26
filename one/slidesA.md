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

        @player = Player.create
      end
      
      def update
        super
        self.caption = "FPS: #{self.fps}"
      end
    end

!SLIDE

## Player

    @@@ ruby
    class Player < Chingu::GameObject  
      def initialize
        super
        self.x = 200
        self.y = 200
        self.image = Image["ship.png"]
        self.input = {:holding_left => :move_left,
                      :holding_right => :move_right}
      end

      def move_left;  @x -= 3; end
      def move_right; @x += 3; end
    end
	
!SLIDE bullets

## Input

    @@@ ruby
    self.input => {:holding_x => :command}

    :holding_x  => :every_frame
    :x          => :key_down
    :released_x => :key_up


!SLIDE bullets

## Sound

    @@@ ruby
    Sound["blaster.wav"].play
  
!SLIDE smbullets

## Traits (aka modules)

* Timers
* Collision
* BoundingArea (Square/Circle)
* Velocity
* Animation

!SLIDE smbullets

## States

* Your basic stack to manage menus, levels, pausing.


!SLIDE

## Put it all together!


!SLIDE smbullets

## Resources

* Sound
  * www.bfxr.net (Random SFX Generator)
  * www.freesound.org (Categorized sound clips)

* Music
  * www.soundcloud.com (Creative Commons)
  * www.freemusicarchive.org (Creative Commons)

* Graphics
  * www.pixeljoint.com (8-bit artist community)
  * www.deviantart.com (Search 'sprite', Commisions)

!SLIDE bullets center transition=scrollUp
# EOF #
Thanks!

* github.com/zeroeth
* twitter.com/kevinalford
* pixelflow.org

