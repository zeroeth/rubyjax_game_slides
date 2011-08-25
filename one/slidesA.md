!SLIDE title-slide
# Having Fun
# in Ruby

!SLIDE bullets
# First Slide #

* blah blah
* blah

!SLIDE bullets
# Next Slide #

* two
* three

!SLIDE
# Third Slide #
    @@@ ruby
    require 'sinatra/base'

    class MyApp < Sinatra::Base
      set :sessions, true
      set :foo, 'bar'

      get '/' do
	'Hello world!'
      end
    end	

!SLIDE bullets center transition=scrollLeft
# EOF #
Thanks!

* github.com/zeroeth
* twitter.com/kevinalford
* pixelflow.org

