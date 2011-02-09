!SLIDE

# Extending Jekyll #

!SLIDE bullets

# Plugins #

* Generators: create additional content
* Convertors: new markup languages
* Tags: custom tags for liquid \(eg. highlight, include\)
* Place them in the _plugins directory

!SLIDE code smaller

    @@@ ruby
    require 'sass'
    module Jekyll
      class ScssConverter < Converter
        safe true
        priority :low
        
        def matches(ext)
          ext =~ /scss/i
        end
        
        def output_ext(ext)
          ".css"
        end
        
        def convert(content)
          engine = Sass::Engine.new(content, 
                                    :syntax => :scss, 
                                    :style  => :compressed)
          engine.render
        end
      end  
    end
